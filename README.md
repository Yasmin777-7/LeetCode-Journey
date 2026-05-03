```java
class Solution {
    public int romanToInt(String s) {
        int toplam = 0;

        for (int i = 0; i < s.length(); i++) {
            int simdiki = deger(s.charAt(i));

            if (i < s.length() - 1) {

                int sonraki = deger(s.charAt(i + 1));

                if (simdiki < sonraki) {
                    toplam -= simdiki;
                } else {
                    toplam += simdiki;
                }
            } else {
                toplam += simdiki;
            }
        }

        return toplam;
    }

    public int deger(char c) {
        if (c == 'I') return 1;
        if (c == 'V') return 5;
        if (c == 'X') return 10;
        if (c == 'L') return 50;
        if (c == 'C') return 100;
        if (c == 'D') return 500;
        if (c == 'M') return 1000;
        return 0;
    }
}
