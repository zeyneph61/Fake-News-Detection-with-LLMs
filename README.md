# Fake-News-Detection-with-LLMs

//Türkçe 
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

//English

1. Project Description

This project investigates the capabilities of large language models (LLMs) in generating and detecting fake news in Turkish and English. Existing fact-verification systems predominantly rely on cross-referencing news content with external, reliable information sources. However, these approaches depend on static or outdated datasets and provide limited insight into how LLMs internally generate misinformation.

In contrast, this project adopts a “learning from generation” approach, focusing not only on detecting fake news but also on examining how such content is produced by different models. Using recent techniques such as VLPrompt, Fighting Fire with Fire (F3), Catching Chameleons, and SheepDog, the project generates synthetic fake news datasets in Turkish and English and evaluates the degree to which different models can recognize manipulative content produced by each other.

This work aims to address key gaps in the literature: the lack of a comprehensive LLM-based Turkish fake news dataset, the methodological limitations of traditional fact-checking procedures, and the insufficient exploration of cross-model detection performance. By doing so, the project contributes to the development of more resilient detection mechanisms against multi-source misinformation environments.

2. Objectives and Research Questions

The primary objective of this project is to evaluate how effectively large language models can detect fake news generated using various prompt strategies in both Turkish and English. The study analyzes each model’s ability to recognize content produced by itself as well as by other models.

Key research questions include:

Does language (Turkish vs. English) affect the performance of generation and detection tasks?

To what extent can different models detect fake news generated by other models?

How do production and detection behaviors change when identical prompt strategies are applied across models?

How do prompt variations (VLPrompt variants, style attacks, creative prompts) influence generation quality and detection metrics?

The project proposes an experimental framework that systematically examines both production and detection aspects of LLM-generated misinformation.

3. Methodology and Work Packages

The project is structured around five main work packages:

Literature Review and Methodological Framework
Analysis of F3, VLPrompt, Catching Chameleons, SheepDog, and HiSS; identification of generation and detection strategies.

Construction of Real News Dataset
Collection, cleaning, and structuring of real Turkish and English news texts from reliable sources.

Fake News Generation
Use of VLPrompt variants and other prompt techniques to generate fake news with GPT, Gemini, Claude, and LLaMA.
Each synthetic sample is tagged with generation model, prompt type, language, and additional metadata.

Cross-Model Detection Experiments
Evaluation of how effectively each model detects both its own and other models’ fake news outputs using accuracy, precision, recall, and F1-score.

Analysis, Visualization, and Explainability
Quantitative comparison of detection results, generation-performance relationships, and explainability analyses using methods such as LIME and SHAP.

This framework directly targets three major gaps in the field:
the lack of a Turkish LLM-based misinformation dataset, methodological dependency on external fact sources, and insufficient research on model-level awareness between LLMs.

4. Repository Structure
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


Folder descriptions:

literature/: Research papers and literature review notes

datasets/: Real and synthetic fake news datasets (TR/EN)

prompt_templates/: Standardized TR/EN prompt templates

model_outputs/: Generated fake news outputs and model logs

notebooks/: Jupyter notebooks for data processing, analysis, and visualization

evaluation/: Metrics, evaluation graphs, confusion matrices

scripts/: Data collection, generation, detection, and evaluation scripts

5. Models Used

The project employs both commercial and open-source LLMs:

OpenAI GPT models

Google Gemini models

Anthropic Claude models

Meta LLaMA (local execution)

These models are compared in terms of both generation behavior and detection accuracy.

6. Installation

Install required Python packages:

pip install -r requirements.txt


All notebooks can be executed through Jupyter or VS Code.

7. License

This project is distributed under the MIT License.
Users may use, modify, and redistribute the code and datasets provided that the license text is preserved.

8. Research Team

Project Lead: Zeynep Hacısalioğlu
Advisor: Yılmaz Ar
Institution: Ankara University

This study is conducted under the TÜBİTAK 2209-A Undergraduate Research Support Program.
