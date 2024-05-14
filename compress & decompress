# Nén dữ liệu
def compress(origin):
    dictionary = {chr(i) : i for i in range(256)}
    dic_size = 255
    result = []
    carry = ""
    for v in origin:
        nextcarry = carry + v
        if nextcarry in dictionary:
            carry = nextcarry
        else:
            result.append(dictionary[carry])
            carry = v
            dic_size += 1
            dictionary[nextcarry] = dic_size 
    result.append(dictionary[carry])
    return result
    
    
    
# Giải nén
def decompress(compressed):
    dictionary_size = 256
    dictionary = {i: chr(i) for i in range(dictionary_size)}

    result = []
    w = chr(compressed.pop(0))
    result.append(w)
    
    for k in compressed:
        if k in dictionary:
            entry = dictionary[k]
        else:
            entry = w + w[0]
        result.append(entry)
        dictionary[dictionary_size] = w + entry[0]
        dictionary_size += 1

        w = entry   

    return ''.join(result)
        
    
origin = input()
compressed = compress(origin) 
print("Compressed:",compressed)
decompressed = decompress(compressed)
print("Decompress:",decompressed)
