# Bài 2
Chuyển chuỗi số nguyên sang int value. Ví dụ “5646” thành int = 5646.  

Gợi ý: Dùng Integer wrapper class để convert string sang int nhanh chóng.


Các bạn mở file `Excersize7.java` và tự code thử đi nha, xong rồi biên dịch và chạy thử

<details>
    <summary>Lời giải</summary>
    ```

        public class Excersize7 {

            public static void main(String[] args) {
                String str = "123";
                int i1 = Integer.valueOf(str);
                System.out.println(i1);

            }

        }

    ```
</details>