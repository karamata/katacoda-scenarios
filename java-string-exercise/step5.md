# Bài 5
Kiểm tra một chuỗi có chứa chữ số hay không, nếu có in ra false ngược lại true.

Ví dụ

“abc”, “” => true

“1abc”, “abc1”, “123”, “a1bc”, null => false

Gợi ý: Sử dụng java regex nếu bạn quen với việc sử dụng chúng. Đây cũng là cách ngắn gọn nhất. Hoặc bạn có thể loop và kiểm tra từng ký tự trong chuỗi.


Các bạn mở file `Excersize5.java` và tự code thử đi nha, xong rồi biên dịch và chạy thử

<details>
    <summary>Lời giải</summary>
    ```
        import java.util.regex.Pattern;

        public class Excersize5 {

            public static void main(String[] args) {
                System.out.println(isContainsNumber1("acbdefgh"));
                System.out.println(isContainsNumber1("acbde4fgh"));
                System.out.println(isContainsNumber1("acbdefgh23"));
                System.out.println(isContainsNumber1("123acbdefgh"));
                System.out.println(isContainsNumber1(""));
                System.out.println(isContainsNumber1(null));

                System.out.println("---------------------------------------");

                System.out.println(isContainsNumber2("acbdefgh"));
                System.out.println(isContainsNumber2("acbde4fgh"));
                System.out.println(isContainsNumber2("acbdefgh23"));
                System.out.println(isContainsNumber2("123acbdefgh"));
                System.out.println(isContainsNumber2(""));
                System.out.println(isContainsNumber2(null));

            }

            // Su dung java regex
            public static boolean isContainsNumber1(String str) {
                if (str == null) {
                    return false;
                }
        //        Pattern pattern = Pattern.compile("[^0-9]*");
                // or
                Pattern pattern = Pattern.compile("\\D*");
                return pattern.matcher(str).matches();
            }

            // Loop va check
            public static boolean isContainsNumber2(String str) {
                if (str == null) {
                    return false;
                }
                for (int i = 0; i < str.length(); i++) {
                    if (Character.isDigit(str.charAt(i))) {
                        return false;
                    }
                }

                return true;
            }

        }

    ```
</details>