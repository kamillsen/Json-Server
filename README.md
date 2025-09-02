# Filo API Projesi

Bu proje, araç (filo) verileri için hızlı bir şekilde sahte (mock) bir REST API oluşturmak amacıyla `json-server` kullanır.

## Sunucuyu Çalıştırma

Proje, `npm run dev` komutu ile çalışacak şekilde yapılandırılmıştır. Sunucuyu başlatmak için proje dizininde aşağıdaki komutu çalıştırmanız yeterlidir:

```bash
npm run dev
```

Bu komut, sunucuyu `http://localhost:3001` adresi üzerinden başlatır. Sunucuyu durdurmak için terminalde `Ctrl+C` yapabilirsiniz.

---

## API Kullanımı ve Yetenekleri

Sunucu çalıştırıldıktan sonra, `vehicles` kaynağı için aşağıdaki standart RESTful endpoint'ler otomatik olarak kullanılabilir hale gelir.

### Temel İşlemler

*   **Tüm araçları listeleme:**
    *   `GET /vehicles`
*   **Belirli bir aracı getirme:**
    *   `GET /vehicles/1`
*   **Yeni bir araç ekleme:**
    *   `POST /vehicles` (Request body'de JSON formatında yeni araç verisi gönderilir)
*   **Bir aracı tamamen güncelleme:**
    *   `PUT /vehicles/1`
*   **Bir aracı kısmen güncelleme:**
    *   `PATCH /vehicles/1`
*   **Bir aracı silme:**
    *   `DELETE /vehicles/1`

### Gelişmiş Sorgulama (`json-server` Özellikleri)

`json-server`, kod yazmadan gelişmiş sorgulamalar yapmanıza olanak tanır.

*   **Filtreleme:** Kaynakları özelliklerine göre filtreleyebilirsiniz.
    *   *Örnek: Sadece "Ford" marka araçları getirmek için:*
        `GET /vehicles?marka=Ford`
    *   *Örnek: 2022 yılından daha yeni araçları getirmek için (`_gt` = greater than):*
        `GET /vehicles?yıl_gt=2022`

*   **Sıralama:** Sonuçları belirli bir özelliğe göre sıralayabilirsiniz.
    *   *Örnek: Araçları yıla göre artan şekilde sıralamak için (`_sort`, `_order`):*
        `GET /vehicles?_sort=yıl&_order=asc`
    *   *Örnek: Markaya göre azalan şekilde sıralamak için:*
        `GET /vehicles?_sort=marka&_order=desc`

*   **Sayfalama:** Büyük veri setlerini sayfalar halinde alabilirsiniz.
    *   *Örnek: İlk sayfadaki 5 aracı getirmek için (`_page`, `_limit`):*
        `GET /vehicles?_page=1&_limit=5`

*   **Metin Arama:** Tüm alanlarda metin araması yapabilirsiniz.
    *   *Örnek: İçinde "Focus" geçen kayıtları bulmak için (`q`):*
        `GET /vehicles?q=Focus`
