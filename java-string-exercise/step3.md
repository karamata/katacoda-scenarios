# Bài 3
Tìm ký tự chỉ xuất hiện một lần trong chuỗi, nếu có nhiều hơn một thì xuất ra màn hình ký tự đầu tiên. Nếu không có ký tự nào unique xuất ra “NO”.

Gợi ý:

    Sử dụng LinkedHashMap. 
    HashMap kết hợp với duyệt lại chuỗi để tìm ra ký tự đầu tiên xuất hiện một lần.


Các bạn mở file `Excersize3.java` và tự code thử đi nha, xong rồi biên dịch và chạy thử

<details>
    <summary>Lời giải</summary>
    ```
    
        import java.util.HashMap;
        import java.util.LinkedHashMap;
        import java.util.Map;


        public class Excersize3 {

            public static void main(String[] args) {
                findNonRepeat1("java");
                findNonRepeat1("siwss");
                findNonRepeat1("hello");

                System.out.println("--------------------------------------");

                findNonRepeat2("java");
                findNonRepeat2("siwss");
                findNonRepeat2("hello");

            }

            public static void findNonRepeat1(String str) {
                if (str == null || str.isEmpty()) {
                    System.out.println("NO");
                }

                LinkedHashMap<Character, Integer> map = new LinkedHashMap<>();
                for (int i = 0; i < str.length(); i++) {
                    if (map.containsKey(str.charAt(i))) {
                        map.compute(str.charAt(i), (k, v) -> v + 1);
                    } else {
                        map.put(str.charAt(i), 1);
                    }
                }

                for (Map.Entry<Character, Integer> entry : map.entrySet()) {
                    if (entry.getValue() == 1) {
                        System.out.println(entry.getKey());
                        return;
                    }
                }
                System.out.println("NO");
            }

            public static void findNonRepeat2(String str) {
                if (str == null || str.isEmpty()) {
                    System.out.println("NO");
                }

                HashMap<Character, Integer> map = new HashMap<>();
                for (int i = 0; i < str.length(); i++) {
                    if (map.containsKey(str.charAt(i))) {
                        map.compute(str.charAt(i), (k, v) -> v + 1);
                    } else {
                        map.put(str.charAt(i), 1);


                    }
                }

                for (int i = 0; i < str.length(); i++) {
                    if (map.get(str.charAt(i)) == 1) {
                        System.out.println(str.charAt(i));
                        return;
                    }
                }
            }


        }

    ```
</details>