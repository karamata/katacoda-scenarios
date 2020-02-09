# Bài 2
Kiểm tra 2 chuỗi có là đảo ngược của nhau hay không. Nếu có xuất ra “OK” ngược lại “KO”. Ví dụ “word” và “drow” là 2 chuỗi đảo ngược nhau.

Các bạn mở file `Excersize2.java` và tự code thử đi nha, xong rồi biên dịch và chạy thử

<details>
    <summary>Lời giải</summary>
    ```

        public class Excersize2 {

            public static void main(String[] args) {
                System.out.println(isAnagram1("word", "drow"));

                System.out.println(isAnagram1("share", "haresdf"));

                System.out.println(isAnagram1("word", ""));

                System.out.println(isAnagram1("word", null));

                System.out.println("--------------------------------------------");


                System.out.println(isAnagram2("word", "drow"));

                System.out.println(isAnagram2("share", "haresdf"));

                System.out.println(isAnagram2("word", ""));

                System.out.println(isAnagram2("word", null));

            }

            // Su diung String Builder duoc java cung cap san merhod reverse()
            public static boolean isAnagram1(String first, String second) {
                if (first == null || second == null) {
                    return false;
                }

                if (first.length() != second.length()) {
                    return false;
                }

                StringBuilder builder = new StringBuilder(second);
                return first.equals(builder.reverse().toString());
            }


            // So sanh tung doi i va len - i neu tat ca cac cap deu trung nhau thi chung nguoc nhau(len do dai str)
            public static boolean isAnagram2(String first, String second) {

                if (first == null || second == null) {
                    return false;
                }

                if (first.length() != second.length()) {
                    return false;
                }

                int len = first.length();
                for (int i = 0; i < len; i++) {
                    if (first.charAt(i) != second.charAt(len - 1 - i)){
                        return false;
                    }
                }
                return true;
            }

        }

    ```
</details>