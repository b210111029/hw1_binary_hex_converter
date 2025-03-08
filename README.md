# hw1_binary_hex_converter
# 十進位轉二進位
def to_binary(n):
    bit_0 = n % 2
    bit_1 = (n // 2) % 2
    bit_2 = (n // 4) % 2
    bit_3 = (n // 8) % 2
    bit_4 = (n // 16) % 2
    bit_5 = (n // 32) % 2
    bit_6 = (n // 64) % 2
    bit_7 = (n // 128) % 2

    binary = str(bit_7) + str(bit_6) + str(bit_5) + str(bit_4) + str(bit_3) + str(bit_2) + str(bit_1) + str(bit_0)
    
    return binary

# 十進位轉十六進位
def to_hexadecimal(binary):
    hex_chars = "0123456789ABCDEF"

    binary = binary.zfill(8)
  
    group1 = binary[:4]
    group2 = binary[4:]
    
    hex_value = hex_chars[int(group1, 2)] + hex_chars[int(group2, 2)]
    
    return hex_value

# 輸入十進位數字
decimal_number = int(input("請輸入一個 0 到 255 的十進位數字: "))

if 0 <= decimal_number <= 255:
    binary = to_binary(decimal_number)  
    hexadecimal = to_hexadecimal(binary)  
    
    print(f"二進位: {binary}")
    print(f"十六進位: {hexadecimal}")
else:
    print("請輸入一個有效的數字（0 到 255 之間）。")
