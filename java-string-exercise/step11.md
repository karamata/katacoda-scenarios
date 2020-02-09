# Bài 2
Cho một chuỗi str, xoá các ký tự xuất hiện nhiều hơn một lần trong chuỗi và chỉ giữ lại ký tự đầu tiên, vi dụ bananas => bans

Gợi ý: Sử dụng HashSet hoặc ArrayList lưu các ký tự đã xuất hiện trong lúc duyệt. Nếu ký tự được duyệt chưa có tỏng HashSet hoặc ArrayList thì cộng ký tự đó vào chuỗi kết quả và thêm ký tự đó vào HashSet hoặc ArrayList. Lưu ý sử dụng StringBuilder hoặc StringBuffer để thao tác cộng chuỗi.


Các bạn mở file `Excersize11.java` và tự code thử đi nha, xong rồi biên dịch và chạy thử

<details>
    <summary>Lời giải</summary>
    ```

        public class Excersize11 {

            public static void main(String[] args) {
                System.out.println(removeDuplicateChar("bananas"));
                System.out.println(removeDuplicateChar(""));

            }

            public static String removeDuplicateChar(String str) {
                Set<Character> charsPresent = new HashSet<>();
                StringBuilder stringBuilder = new StringBuilder();
                for(int i = 0; i < str.length(); i++) {
                    if (!charsPresent.contains(str.charAt(i))) {
                        stringBuilder.append(str.charAt(i));
                        charsPresent.add(str.charAt(i));
                    }
                }

                return stringBuilder.toString();
            }

        }

    ```
</details>