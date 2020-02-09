# Bài 2
Viết chương trình tìm độ dài chuỗi con lớn nhất mà các ký tự không trùng lặp.

Ví dụ: “pickoutthelongestsubstring” => “ubstring”. 

Gợi ý: Sử dụng LinkedHashMap<Character, Integer>(key là ký tự tại vị trí index là value) duyệt qua từng ký tự trong chuỗi và kiểm tra.


Các bạn mở file `Excersize14.java` và tự code thử đi nha, xong rồi biên dịch và chạy thử

<details>
    <summary>Lời giải</summary>
    ```
        import java.util.LinkedHashMap;

        public class Excersize14 {
            static void longestSubstring(String inputString) {
                char[] arr1 = inputString.toCharArray();
                String long_str = null;
                int str_length = 0;
                // character at index i
                // LinkedHashMap for sure index follow to order
                LinkedHashMap<Character, Integer> charPosMap = new LinkedHashMap<>();
                for (int i = 0; i < arr1.length; i++) {
                    char ch = arr1[i];
                    if (!charPosMap.containsKey(ch)) {
                        charPosMap.put(ch, i);
                    } else {
                        i = charPosMap.get(ch);
                        charPosMap.clear();
                    }
                    if (charPosMap.size() > str_length) {
                        str_length = charPosMap.size();
                        long_str = charPosMap.keySet().toString();
                    }
                }
                System.out.println("Input String : " + inputString);
                System.out.println("The longest substring : " + long_str);
                System.out.println("The longest Substring Length : " + str_length);
            }
            public static void main(String[] args) {
                    longestSubstring("pickoutthelongestsubstring");
            }

        }

    ```
</details>