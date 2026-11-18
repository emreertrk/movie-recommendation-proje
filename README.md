Bu alıştırmaya başlamak için, bu alıştırma klasöründeki **IPython Notebook dosyasını** `jupyter notebook` komutu ile açın.

## Çalışma Notları

Bu proje, MovieLens küçük veri setiyle içerik tabanlı, işbirlikçi ve hibrit film öneri yöntemlerini karşılaştırır. Notebook şablondaki adıyla (`recommender-system.ipynb`), kendi kodumla yeniden yazıldı.

1. Ortam: `workintech` sanal ortamı. Proje klasöründe `pyenv local workintech` ile etkinleştirilir.
2. Veriyi `data/` klasörüne indir. Uzak dosyaların adları içerikleriyle karışık olduğu için doğru adlarla kaydet:
   ```bash
   curl -L https://d32aokrjazspmn.cloudfront.net/materials/movie_titles.csv -o data/movies.csv
   curl -L https://d32aokrjazspmn.cloudfront.net/materials/movie_tags.csv -o data/tags.csv
   curl -L https://d32aokrjazspmn.cloudfront.net/materials/movie_ratings.csv -o data/ratings.csv
   ```
   CSV dosyaları `.gitignore` içindedir, repoda yoktur.
3. `jupyter notebook` ile notebook'u aç ve hücreleri sırayla çalıştır. Birkaç saniye sürer.

Özet: İçerik matrisi (etiket + tür, 1675 kelime) 25 bileşene, puan matrisi (9724 film × 610 kullanıcı) 200 bileşene indirildi. Toy Story için içerik tabanlı yöntem yalnızca türü aynı, çoğu az izlenmiş filmleri, işbirlikçi yöntem aynı dönemin popüler aksiyon filmlerini, hibrit yöntem ise Toy Story 2-3, Monsters Inc., Finding Nemo gibi hem tür hem kitle olarak uyumlu filmleri öneriyor. 12 film serisinde hibrit ve işbirlikçi yöntem seri filmlerini benzer oranda yakalıyor (22 ve 21 / 53), içerik tabanlı 7'de kalıyor; hibrit önerilerin tamamı aranan filmle tür paylaşıyor. Ayrıntılar ve sınırlılıklar notebook'un sonuç bölümünde.
