# HELLO JAVA

package ch01;  //第一行是一開始命名的package名稱

public class class01 { //而這行是命名的Class名稱

	public static void main(String[] args) { // 這部分是上方教學要求打勾

		 System.out.println("Hello Java!"); //這部分是Hello Java 程式碼

	}
}

我們由一開始的Project、Package 與 Class 先做簡單說明：

Project 就像是一個課本
package 像是章節
class 就是每章節的內容

project → package → class

# START

public static void main(String[] args)

這是程式的起點。
當程式載入一個 .java 檔，會先去尋找 main 在哪，所以必須先宣告 main 是 公開、共用的 (public)，否則程式將會找不到 main 的位置。

main() 是相當特殊的一個函數，沒有回傳值，因此在main 之前要加上 void。

main() 括號內的String[ ] args 則是：程式執行時，裡面將會以字串型態的陣列 args[] 存放。

# CODE

public class class01 {
	public static void main(String[] args) {
}}

所以整段程式碼可以解釋為：

宣告一個公開的類別 class01， 定義 公開 靜態無傳回值 名稱為main 參數為字串陣列 的方法

# PRINT HELLO WORLD

System.out.println("Hello Java!");

System.out.println( ) 的功用是：印出括號內所有包含的文字。

System.out 意指標準輸出；
後方的 println 則是 print line 的縮寫。