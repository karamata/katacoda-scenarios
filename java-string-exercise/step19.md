# Bài 19
Cho 2 string, gắn chúng lại với nhau, nếu 2 chuỗi có độ dài không bằng nhau thì tiến hành cắt bỏ các ký tự đầu của string dài hơn cho đến khi chúng bằng nhau thì tiến hành gắn lại. Ví dụ Welcome và home => comehome.


Các bạn mở file `Excersize19.java` và tự code thử đi nha, xong rồi biên dịch và chạy thử

<details>
    <summary>Lời giải</summary>
    ```

        public class Excersize19 {

            public static String minCat(String st1, String st2) {
                if (st1.length() == st2.length())
                    return st1+st2;
                if (st1.length() > st2.length()) {
                    int diff = st1.length() - st2.length();
                    return st1.substring(diff, st1.length()) + st2;
                } else {
                    int diff = st2.length() - st1.length();
                    return st1 + st2.substring(diff, st2.length());
                }
            }
            public static void main (String[] args) {
                String str1 =  "Welcome";
                String str2 =  "home";

                System.out.println("The given strings is: "+ str1+" and "+str2);
                System.out.println("The new string is: "+ minCat(str1,str2));
            }

        }

    ```
</details>