# Bài 1
Tìm và in ra các ký tự xuất hiện nhiều hơn một lần trong String cho trước không phân biệt chữ hoa hay chữ thường. Nếu các ký tự trong chuỗi đều là duy nhất thì xuất ra “NO”. Ví dụ chuỗi “Java” thì có ký tự ‘a’ hoặc String “JaVA” cũng có kết quả tương tự.

Gợi ý: Sử dụng [HashMap](https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html)

Các bạn mở file `Excersize1.java` và tự code thử đi nha, xong rồi biên dịch và chạy thử

<details>
    <summary>Lời giải</summary>
    ```
    
        import java.util.HashMap;

        public class Excersize1 {

            public static void main(String[] args) {
                findDuplicateChar(null);
                findDuplicateChar("Java");
                findDuplicateChar("Programming");
                findDuplicateChar("Combination");
                findDuplicateChar("");
            }

            public static void findDuplicateChar(String str) {
                if (str == null || str.isEmpty()) {
                    System.out.println("NO");
                    return;
                }

                String original = str;
                // Chuyen chuoi thanh chu thuong
                str = str.toLowerCase();

                HashMap<Character, Integer> map = new HashMap<>();
                for (int i = 0; i < str.length(); i++) {
                    if (map.containsKey(str.charAt(i))) {
                        map.compute(str.charAt(i), (k, v) -> v + 1);
                    } else {
                        map.put(str.charAt(i), 1);
                    }
                }

                if (map.isEmpty()) {
                    System.out.println("NO");
                    return;
                }

                System.out.println("List duplicate of " + original + ": ");
                map.forEach((k, v) -> {
                    if (v > 1) {
                        System.out.println(k);
                    }
                });

            }
        }

    ```
</details>