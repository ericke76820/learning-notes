# package 套件

舉例來說，一個應用程式中會有多個類別彼此合作，也有可能由多個團隊共同分工，完成應用程式的某些功能塊，再組合在一起，若應用程式是多個團隊共同合作，又不分門別類放置 .class，那麼若 A 部門寫了 Util 類別並編譯為 Util.class，B 部門也寫了 Util 類別並編譯為 Util.class，當他們要將應用程式整合時，就會發生檔案覆蓋的問題，若現在要統一管理原始碼，也許原始碼也會發生彼此覆蓋問題。

你要有個分門別類管理類別的方式，無論是實體檔案上的分類管理，或是類別名稱上的分類管理，有個 package 關鍵字，可以達到這個目的。

# example:
package src.tutorial.example;

public class EX1 {
    public static void writeLine(String text) {
        System.out.println(text);
    }
}

這表示，EX1 類別將放在 src.tutorial.example 套件（package）管理，套件的命名，通常會用組織或單位的網址命名，舉例來說，我的網址是 tutorial.src，套件就會反過來命名為 src.tutorial，由於組織或單位的網址是獨一無二的，這樣的命名方式，比較不會與其他組織或單位的套件發生同名衝突。

接著編輯 另一份 Main.java，在開頭鍵入 package 該行文字，這表示 Main 類別將放在 src.tutorial 套件 ，並且將EX1 改為 src.tutorial.example.EX1：

# example2:

package src.tutorial;

public class Main {
    public static void main(String[] args) {
        src.tutorial.example.EX1.writeLine("Hello, World");
    }
}
