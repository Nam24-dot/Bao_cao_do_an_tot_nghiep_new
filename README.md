Key: 00 11 22 33 44 55 66 77 88 99 AA BB CC DD EE FF

Input block: 01 23 45 67 89 AB CD EF FE DC BA 98 76 54 32 10


Ciphertext sau khi mã hóa là:

9E 12 B5 D9 C6 37 92 F0 9F 4C B5 BD D3 11 17 74

thì chia thành 4 word 32-bit như sau:

RESULT0 = 9E12B5D9

RESULT1 = C63792F0

RESULT2 = 9F4CB5BD

RESULT3 = D3111774

Trên board DE10 Standard, quan sát như này:

SW[9:8] = 00 -> chọn RESULT0 = 9E12B5D9

SW[9:8] = 01 -> chọn RESULT1 = C63792F0

SW[9:8] = 10 -> chọn RESULT2 = 9F4CB5BD

SW[9:8] = 11 -> chọn RESULT3 = D3111774

Trong mỗi word:

SW[7:6] = 00 -> LED hiện byte thấp nhất
SW[7:6] = 01 -> LED hiện byte tiếp theo
SW[7:6] = 10 -> LED hiện byte tiếp theo
SW[7:6] = 11 -> LED hiện byte cao nhất

Cụ thể:

RESULT0 = 9E 12 B5 D9

SW[9:8]=00, SW[7:6]=00 -> D9 (1101 1001)

SW[9:8]=00, SW[7:6]=01 -> B5 (1011 0101)

SW[9:8]=00, SW[7:6]=10 -> 12 (0001 0010)

SW[9:8]=00, SW[7:6]=11 -> 9E (1001 1110)

RESULT1 = C6 37 92 F0

SW[9:8]=01, SW[7:6]=00 -> F0 (1111 0000)

SW[9:8]=01, SW[7:6]=01 -> 92 (1001 0010)

SW[9:8]=01, SW[7:6]=10 -> 37 (0011 0111)

SW[9:8]=01, SW[7:6]=11 -> C6 (1100 0110)

RESULT2 = 9F 4C B5 BD

SW[9:8]=10, SW[7:6]=00 -> BD (1011 1101)

SW[9:8]=10, SW[7:6]=01 -> B5 (1011 0101)

SW[9:8]=10, SW[7:6]=10 -> 4C (0100 1100)

SW[9:8]=10, SW[7:6]=11 -> 9F (1001 1111)

RESULT3 = D3 11 17 74

SW[9:8]=11, SW[7:6]=00 -> 74 (0111 0100)

SW[9:8]=11, SW[7:6]=01 -> 17 (0001 0111)

SW[9:8]=11, SW[7:6]=10 -> 11 (0001 0001)

SW[9:8]=11, SW[7:6]=11 -> D3 (1101 0011)
