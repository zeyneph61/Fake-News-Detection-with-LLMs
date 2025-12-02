1. Projenin Tanımı

Bu proje, büyük dil modellerinin (LLM) Türkçe ve İngilizce sahte haber üretimi ile sahte haber tespit performansını çok yönlü biçimde inceleyen bir araştırmadır. Literatürdeki mevcut sahte haber doğrulama yaklaşımlarının büyük bir kısmı, haberlerin doğruluğunu dış kaynaklarla karşılaştırma yöntemine dayanmaktadır. Ancak bu yöntem hem güncel olmayan veri kaynaklarına bağımlıdır hem de büyük dil modellerinin üretim süreçlerini anlamada sınırlılık taşımaktadır.

Bu proje, doğrulamadan ziyade “üretimden öğrenme” (learning from generation) yaklaşımını benimser. Bu kapsamda sahte haberlerin yalnızca tespit edilmesi değil, aynı zamanda bu içeriklerin nasıl üretildiğinin anlaşılması hedeflenmektedir. VLPrompt, Fighting Fire with Fire (F3), Catching Chameleons ve SheepDog gibi güncel yöntemler temel alınarak Türkçe ve İngilizce sahte haber veri setleri üretilecek ve farklı modellerin bu sahte içerikleri ne ölçüde tanıyabildiği incelenecektir.

Bu çalışma, Türkçe dilinde LLM tabanlı kapsamlı bir sahte haber veri seti eksikliğini gidermeyi, modeller arası tespit farkındalığını analiz etmeyi ve çok kaynaklı dezenformasyon ortamlarına karşı daha dayanıklı tespit mekanizmaları geliştirilmesine katkı sağlamayı amaçlamaktadır.

2. Projenin Amacı ve Araştırma Soruları

Projenin temel amacı, büyük dil modellerinin farklı prompt stratejileri kullanılarak üretilmiş Türkçe ve İngilizce sahte haberleri hem kendi hem de diğer modeller açısından ne ölçüde tanıyabildiğini ortaya koymaktır.

Bu kapsamda aşağıdaki araştırma sorularına yanıt aranacaktır:

Haber dilinin değişmesi modellerin üretim ve tespit performansını etkiler mi?

Farklı modeller birbirlerinin ürettiği sahte haberleri hangi düzeyde tanıyabilir?

Aynı prompt stratejileri kullanıldığında modellerin üretim biçimleri ve tespit başarıları nasıl değişir?

Prompt varyasyonları (VLPrompt, style attacks, yaratıcı varyantlar) üretim kalitesini ve tespit metriklerini nasıl etkiler?

Bu doğrultuda proje hem üretim sürecini hem tespit performansını deneysel olarak analiz eden özgün bir yaklaşım sunmaktadır.

3. Yöntem ve Çalışma Paketleri

Proje beş temel iş paketi çerçevesinde yürütülmektedir:

Literatür Taraması ve Yöntemsel Çerçevenin Oluşturulması
F3, VLPrompt, Catching Chameleons, SheepDog ve HiSS çalışmalarının incelenmesi; üretim ve tespit stratejilerinin belirlenmesi.

Gerçek Haber Veri Setinin Oluşturulması
Türkçe ve İngilizce güvenilir haber kaynaklarından gerçek haberlerin toplanması, temizlenmesi ve yapılandırılması.

Sahte Haber Üretimi
VLPrompt varyantları ve diğer prompt teknikleri kullanılarak GPT, Gemini, Claude ve LLaMA gibi modellerle sahte haber üretimi.
Her kayıt; üretici model, kullanılan prompt türü, dil ve içerik özellikleri ile etiketlenir.

Modeller Arası Tespit Testleri
Her bir modelin hem kendi hem de diğer modeller tarafından üretilen sahte haberleri ne kadar doğru tespit edebildiği; accuracy, precision, recall ve F1-score metrikleriyle ölçülür.

Analiz, Görselleştirme ve Açıklanabilirlik
Elde edilen sonuçların grafiklerle karşılaştırılması, açıklanabilirlik analizlerinin (ör. LIME-SHAP) yürütülmesi ve raporlanması.

Bu yapı, literatürdeki üç temel boşluğu hedeflemektedir:
Türkçe veri seti eksikliği, yöntemsel kısıtlar ve modeller arası farkındalık analizi eksikliği.

4. Klasör Yapısı

Proje yapısı araştırma, veri, analiz ve model çıktılarının düzenli biçimde konumlandırılabilmesi için aşağıdaki şekilde tasarlanmıştır:

fake-news-llm/
│
├── README.md
├── LICENSE
│
├── literature/
├── datasets/
├── prompt_templates/
├── model_outputs/
├── notebooks/
├── evaluation/
├── scripts/
└── requirements.txt


Her klasörün görevleri:

literature/: Makaleler ve çalışma notları

datasets/: Gerçek ve sentetik sahte haber veri setleri

prompt_templates/: TR/EN prompt şablonları

model_outputs/: Üretilen sahte haberler ve loglar

notebooks/: Veri işleme, analiz ve görselleştirme notebook’ları

evaluation/: Sonuç metrikleri ve grafikler

scripts/: Veri toplama, üretim, tespit ve değerlendirme kodları

5. Kullanılan Modeller

Projede hem API tabanlı hem yerel modellerden yararlanılmaktadır:

OpenAI GPT modelleri

Google Gemini modelleri

Anthropic Claude modelleri

Meta LLaMA (lokal)

Bu modeller üretim, tespit ve analiz süreçlerinde birbirleriyle karşılaştırmalı biçimde değerlendirilmiştir.

6. Kurulum

Gerekli Python paketleri aşağıdaki komut ile kurulabilir:

pip install -r requirements.txt


Notebook dosyaları Jupyter veya VSCode üzerinden çalıştırılabilir.

7. Lisans

Bu proje MIT Lisansı ile yayınlanmıştır.
Kullanan veya yeniden dağıtan herkesin lisans metnini koruması koşuluyla kullanım, değişiklik ve ticari uygulamalar serbesttir.

8. Araştırma Ekibi

Proje Yürütücüsü: Özge Taraşlı, Zeynep Hacısalioğlu
Danışman: Yılmaz Ar
Kurum: Ankara Üniversitesi

Bu proje TÜBİTAK 2209-A Üniversite Öğrencileri Araştırma Projeleri Destek Programı kapsamında yürütülmektedir.
