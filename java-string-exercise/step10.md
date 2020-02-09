# Bài 2
Chuỗi palindrome là chuỗi sau khi đảo ngược và chuỗi ban đầu hoàn toàn giống nhau, ví dụ “aba” là một chuỗi “aba”

Gợi ý: Đảo ngược chuỗi và so sánh với chuỗi ban đầu hoặc loop và so sánh từng cặp chữ một.


Các bạn mở file `Excersize10.java` và tự code thử đi nha, xong rồi biên dịch và chạy thử

<details>
    <summary>Lời giải</summary>
    ```

        public class Excersize10 {

            public static void main(String[] args) {
                System.out.println(isPalindrome1("aaa"));
                System.out.println(isPalindrome1("aba"));
                System.out.println(isPalindrome1("bbbb"));
                System.out.println(isPalindrome1("abcdf"));
                System.out.println(isPalindrome1(null));
                System.out.println(isPalindrome1(""));


                System.out.println("------------------------------");

                System.out.println(isPalindrome2("aaa"));
                System.out.println(isPalindrome2("aba"));
                System.out.println(isPalindrome2("bbbb"));
                System.out.println(isPalindrome2("abcdf"));
                System.out.println(isPalindrome1(null));
                System.out.println(isPalindrome1(""));

                System.out.println("------------------------------");

                System.out.println(isPalindrome3("aaa"));
                System.out.println(isPalindrome3("aba"));
                System.out.println(isPalindrome3("bbbb"));
                System.out.println(isPalindrome3("abcdf"));
                System.out.println(isPalindrome1(null));
                System.out.println(isPalindrome1(""));

            }

            public static boolean isPalindrome1(String input) {
                if (input == null) {
                    return false;
                }
                StringBuilder stringBuilder = new StringBuilder(input);
                return input.equals(stringBuilder.reverse().toString());
            }

            public static boolean isPalindrome2(String input) {
                if (input == null) {
                    return false;
                }
                String reverse = reverse(input);
                return reverse.equals(input);
            }

            public static boolean isPalindrome3(String input) {
                if (input == null) {
                    return false;
                }
                for(int i = 0; i < input.length(); i++) {
                    if (input.charAt(i) != input.charAt(input.length() - 1 - i))
                        return false;
                }
                return true;
            }

            // reverse str de quy
            public static String reverse(String input){
                if(input == null || input.isEmpty()){
                    return input;
                }

                return input.charAt(input.length()- 1) + reverse(input.substring(0, input.length() - 1));
            }

        }

    ```
</details>