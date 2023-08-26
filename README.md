from collections import Counter

def main():
    dosya_adi = input("Metin dosyasının adını girin: ")

    try:
        with open(dosya_adi, 'r') as dosya:
            metin = dosya.read()
            kelimeler = metin.split()
            kelime_sayisi = len(kelimeler)
            
            kelime_sayac = Counter(kelimeler)
            en_cok_gecenler = kelime_sayac.most_common(5)
            
            print(f"Dosyadaki toplam kelime sayısı: {kelime_sayisi}")
            print("En çok geçen kelimeler:")
            for kelime, sayi in en_cok_gecenler:
                print(f"{kelime}: {sayi} kez")

    except FileNotFoundError:
        print("Dosya bulunamadı.")

if __name__ == "__main__":
    main()
