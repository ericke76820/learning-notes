# package 套件

舉例來說，一個應用程式中會有多個類別彼此合作，也有可能由多個團隊共同分工，完成應用程式的某些功能塊，再組合在一起，若應用程式是多個團隊共同合作，又不分門別類放置 .class，那麼若 A 部門寫了 Util 類別並編譯為 Util.class，B 部門也寫了 Util 類別並編譯為 Util.class，當他們要將應用程式整合時，就會發生檔案覆蓋的問題，若現在要統一管理原始碼，也許原始碼也會發生彼此覆蓋問題。

你要有個分門別類管理類別的方式，無論是實體檔案上的分類管理，或是類別名稱上的分類管理，有個 package 關鍵字，可以達到這個目的。

# example:
package net.tutorial.example;

public class EX1 {
    public static void writeLine(String text) {
        System.out.println(text);
    }
}

這表示，EX1 類別將放在 net.tutorial.example 套件（package）管理，套件的命名，通常會用組織或單位的網址命名，舉例來說，我的網址是 tutorial.net，套件就會反過來命名為 net.tutorial，由於組織或單位的網址是獨一無二的，這樣的命名方式，比較不會與其他組織或單位的套件發生同名衝突。

接著編輯 另一份 Main.java，在開頭鍵入 package 該行文字，這表示 Main 類別將放在 net.tutorial 套件 ，並且將EX1 改為 net.tutorial.example.EX1：

# example2:

package net.tutorial;

public class Main {
    public static void main(String[] args) {
        net.tutorial.example.EX1.writeLine("Hello, World");
    }
}

當類別原始碼開始使用 package 進行分類時，就會具有四種管理上的意義：

原始碼檔案要放置在與 package 定義名稱階層相同的資料夾階層。

目前計劃將所有原始碼檔案放在 src 中管理，由於 EX1 類別使用 package 定義在 net.tutorial.example 套件下，EX1.java 就必須放在 src 資料夾中的 net/tutorial/example 資料夾，在沒有工具輔助下，必須手動建立出資料夾，Main 類別使用 package 定義在 net.tutorial 套件下，因此 Main.java 必須放在 src 資料夾中的 net/tutorial 資料夾。

編譯時並不用手動建立對應套件階層的資料夾，若使用 -d 指定位元碼的存放位置，就會自動建立出對應套件階層的資料夾，並將編譯出來的位元碼檔案放置至對應的位置。例如：

# execute a java class file:

PS C:\JAVA> javac -sourcepath src -cp classes -d classes src/net/tutorial/Main.java
PS C:\JAVA> java -cp classes net.tutorial.Main
Hello, World
