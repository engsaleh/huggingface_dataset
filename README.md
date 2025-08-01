<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://huggingface.co/datasets/huggingface/documentation-images/raw/main/datasets-logo-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://huggingface.co/datasets/huggingface/documentation-images/raw/main/datasets-logo-light.svg">
    <img alt="مكتبة Hugging Face Datasets" src="https://huggingface.co/datasets/huggingface/documentation-images/raw/main/datasets-logo-light.svg" width="352" height="59" style="max-width: 100%;">
  </picture>
  <br/>
  <br/>
</p>

<p align="center">
    <a href="https://github.com/huggingface/datasets/actions/workflows/ci.yml?query=branch%3Amain"><img alt="Build" src="https://github.com/huggingface/datasets/actions/workflows/ci.yml/badge.svg?branch=main"></a>
    <a href="https://github.com/huggingface/datasets/blob/main/LICENSE"><img alt="GitHub" src="https://img.shields.io/github/license/huggingface/datasets.svg?color=blue"></a>
    <a href="https://huggingface.co/docs/datasets/index.html"><img alt="Documentation" src="https://img.shields.io/website/http/huggingface.co/docs/datasets/index.html.svg?down_color=red&down_message=offline&up_message=online"></a>
    <a href="https://github.com/huggingface/datasets/releases"><img alt="GitHub release" src="https://img.shields.io/github/release/huggingface/datasets.svg"></a>
    <a href="https://huggingface.co/datasets/"><img alt="عدد مجموعات البيانات" src="https://img.shields.io/endpoint?url=https://huggingface.co/api/shields/datasets&color=brightgreen"></a>
    <a href="CODE_OF_CONDUCT.md"><img alt="Contributor Covenant" src="https://img.shields.io/badge/Contributor%20Covenant-2.0-4baaaa.svg"></a>
    <a href="https://zenodo.org/badge/latestdoi/250213286"><img src="https://zenodo.org/badge/250213286.svg" alt="DOI"></a>
</p>

🤗 مكتبة Datasets هي مكتبة خفيفة الوزن تقدم **ميزتين** رئيسيتين:

- **محمل بيانات بسطر واحد للعديد من مجموعات البيانات العامة**: أوامر بسيطة لتحميل ومعالجة أي من ![عدد مجموعات البيانات](https://img.shields.io/endpoint?url=https://huggingface.co/api/shields/datasets&color=brightgreen) مجموعات البيانات العامة المهمة (صور، صوت، نصوص بـ467 لغة ولهجة، وغيرها) المتوفرة على [مركز HuggingFace Datasets](https://huggingface.co/datasets). باستخدام أمر بسيط مثل `squad_dataset = load_dataset("squad")` يمكنك الحصول على أي مجموعة بيانات جاهزة للاستخدام في التحميل لتدريب أو تقييم نموذج تعلم آلي (دعم Numpy/Pandas/PyTorch/TensorFlow/JAX).
- **معالجة بيانات فعالة**: معالجة بيانات بسيطة، سريعة وقابلة لإعادة الإنتاج لمجموعات البيانات العامة وكذلك مجموعات البيانات المحلية الخاصة بك بصيغ مثل CSV، JSON، نص، PNG، JPEG، WAV، MP3، Parquet، وغيرها. باستخدام أوامر بسيطة مثل `processed_dataset = dataset.map(process_example)` يمكنك تحضير البيانات بكفاءة للفحص والتقييم والتدريب.

[🎓 **التوثيق**](https://huggingface.co/docs/datasets/) [🔎 **البحث عن مجموعة بيانات في المركز**](https://huggingface.co/datasets) [🌟 **مشاركة مجموعة بيانات في المركز**](https://huggingface.co/docs/datasets/share)

<h3 align="center">
    <a href="https://hf.co/course"><img src="https://raw.githubusercontent.com/huggingface/datasets/main/docs/source/imgs/course_banner.png"></a>
</h3>

🤗 تم تصميم مكتبة Datasets لتمكين المجتمع من إضافة ومشاركة مجموعات بيانات جديدة بسهولة.

🤗 تحتوي المكتبة على العديد من الميزات الإضافية المهمة:

- دعم مجموعات بيانات ضخمة: تحررك المكتبة من قيود ذاكرة الرام، حيث تُخزن جميع البيانات باستخدام تقنيات memory-mapping فعالة بدون تكلفة تسلسل (Apache Arrow).
- التخزين المؤقت الذكي: لا تنتظر لمعالجة بياناتك عدة مرات.
- خفيفة وسريعة بواجهة برمجة تطبيقات شفافة وبايثونية (دعم تعدد المعالجات، التخزين المؤقت، وتقنية memory-mapping).
- تكامل أصلي مع NumPy، pandas، PyTorch، TensorFlow 2 و JAX.
- دعم أصلي للبيانات الصوتية والمرئية.
- تفعيل وضع البث (streaming) لتوفير مساحة القرص والبدء في التكرار على البيانات فوراً.

🤗 نشأت مكتبة Datasets من تفريع لمكتبة [TensorFlow Datasets](https://github.com/tensorflow/datasets) المميزة، ويود فريق HuggingFace تقديم الشكر العميق لفريق TensorFlow Datasets على بناء هذه المكتبة الرائعة. يمكنكم معرفة المزيد عن الفروقات بين 🤗 Datasets و `tfds` في القسم [Main differences between 🤗 Datasets and `tfds`](#main-differences-between--datasets-and-tfds).

# التثبيت

## باستخدام pip

يمكن تثبيت مكتبة 🤗 Datasets من PyPi ويُفضل تثبيتها في بيئة افتراضية (مثل venv أو conda):

```bash
pip install datasets
````

## باستخدام conda

يمكن تثبيت المكتبة باستخدام conda كما يلي:

```bash
conda install -c huggingface -c conda-forge datasets
```

راجع صفحات تثبيت TensorFlow وPyTorch لمعرفة كيفية تثبيتهما مع conda.

لمزيد من التفاصيل، راجع صفحة التثبيت في التوثيق: [https://huggingface.co/docs/datasets/installation](https://huggingface.co/docs/datasets/installation)

## التثبيت لاستخدامها مع PyTorch/TensorFlow/pandas

إذا كنت تخطط لاستخدام المكتبة مع PyTorch (1.0+)، TensorFlow (2.2+) أو pandas، يجب عليك أيضًا تثبيت PyTorch أو TensorFlow أو pandas.

للمزيد من التفاصيل حول استخدام المكتبة مع NumPy، pandas، PyTorch أو TensorFlow، راجع صفحة البدء السريع: [https://huggingface.co/docs/datasets/quickstart](https://huggingface.co/docs/datasets/quickstart)

# الاستخدام

تم تصميم 🤗 Datasets لتكون سهلة الاستخدام جدًا — الواجهة تدور حول دالة واحدة فقط:

```python
datasets.load_dataset(dataset_name, **kwargs)
```

تُستخدم هذه المكتبة لتحميل مجموعات بيانات نصية، صور، صوت، وغيرها. مثال سريع لتحميل مجموعة بيانات نصية:

```python
from datasets import load_dataset

# عرض جميع مجموعات البيانات المتاحة
from huggingface_hub import list_datasets
print([dataset.id for dataset in list_datasets()])

# تحميل مجموعة بيانات وطباعة أول مثال في مجموعة التدريب
squad_dataset = load_dataset('squad')
print(squad_dataset['train'][0])

# معالجة مجموعة البيانات - إضافة عمود يحتوي على طول نصوص السياق
dataset_with_length = squad_dataset.map(lambda x: {"length": len(x["context"])})

# معالجة مجموعة البيانات - ترميز نصوص السياق (باستخدام مرمز من مكتبة 🤗 Transformers)
from transformers import AutoTokenizer
tokenizer = AutoTokenizer.from_pretrained('bert-base-cased')

tokenized_dataset = squad_dataset.map(lambda x: tokenizer(x['context']), batched=True)
```

إذا كانت مجموعة البيانات أكبر من مساحة القرص لديك أو لا تريد الانتظار لتحميل البيانات، يمكنك استخدام البث المباشر:

```python
# لاستخدام مجموعة البيانات فوراً وبكفاءة مع البث أثناء التكرار عليها
image_dataset = load_dataset('cifar100', streaming=True)
for example in image_dataset["train"]:
    break
```

للمزيد من التفاصيل حول استخدام المكتبة، راجع صفحة البدء السريع: [https://huggingface.co/docs/datasets/quickstart](https://huggingface.co/docs/datasets/quickstart) وصفحات التوثيق الخاصة بـ:

* تحميل مجموعة البيانات: [https://huggingface.co/docs/datasets/loading](https://huggingface.co/docs/datasets/loading)
* ما تحتويه مجموعة البيانات: [https://huggingface.co/docs/datasets/access](https://huggingface.co/docs/datasets/access)
* معالجة البيانات: [https://huggingface.co/docs/datasets/process](https://huggingface.co/docs/datasets/process)

  * معالجة البيانات الصوتية: [https://huggingface.co/docs/datasets/audio\_process](https://huggingface.co/docs/datasets/audio_process)
  * معالجة البيانات المرئية: [https://huggingface.co/docs/datasets/image\_process](https://huggingface.co/docs/datasets/image_process)
  * معالجة النصوص: [https://huggingface.co/docs/datasets/nlp\_process](https://huggingface.co/docs/datasets/nlp_process)
* البث المباشر: [https://huggingface.co/docs/datasets/stream](https://huggingface.co/docs/datasets/stream)
* كتابة سكريبت تحميل مجموعة البيانات الخاصة بك: [https://huggingface.co/docs/datasets/dataset\_script](https://huggingface.co/docs/datasets/dataset_script)

# إضافة مجموعة بيانات جديدة إلى المركز

لدينا دليل تفصيلي خطوة بخطوة لإضافة مجموعة بيانات جديدة إلى ![عدد مجموعات البيانات](https://img.shields.io/endpoint?url=https://huggingface.co/api/shields/datasets\&color=brightgreen) مجموعات البيانات المتوفرة على [مركز HuggingFace Datasets](https://huggingface.co/datasets).

يمكنك معرفة:

* [كيفية رفع مجموعة بيانات إلى المركز باستخدام متصفح الويب أو Python](https://huggingface.co/docs/datasets/upload_dataset)
* [كيفية رفعها باستخدام Git](https://huggingface.co/docs/datasets/share)

# الفروقات الرئيسية بين 🤗 Datasets و `tfds`

إذا كنت تعرف مكتبة TensorFlow Datasets، إليك أهم الفروقات بينها وبين 🤗 Datasets:

* سكريبتات 🤗 Datasets ليست مدمجة داخل المكتبة بل تُحمّل، تُخزن مؤقتًا، وتُحمّل ديناميكيًا عند الطلب.
* ترميز البيانات في الخلفية يستخدم [Apache Arrow](https://arrow.apache.org/) بدلًا من TF Records ويستخدم python dataclasses للمعلومات والخصائص مع بعض الاختلافات (لا نقوم بالكثير من الترميز ونخزن البيانات الخام قدر الإمكان).
* كائن مجموعة البيانات الظاهر للمستخدم في 🤗 Datasets ليس `tf.data.Dataset` بل فئة dataset مستقلة عن أي إطار عمل، مستوحاة من بعض مميزات `tf.data` (مثل دالة `map()`)، وتغلف ذاكرة مؤقتة باستخدام Apache Arrow.

# تنبيهات أمنية

قد تقوم مكتبة 🤗 Datasets بتشغيل أكواد Python من مؤلفي مجموعات البيانات لتحليل بعض صيغ أو تراكيب البيانات. لأسباب أمنية، نطلب من المستخدمين:

* مراجعة سكريبتات مجموعات البيانات التي سيستخدمونها مسبقًا
* تثبيت نسخة `revision` معينة من المستودعات التي يستخدمونها

إذا كنت مالكًا لمجموعة بيانات وترغب بتحديث أي جزء منها (الوصف، الاستشهاد، الرخصة، إلخ) أو عدم رغبتك في أن تكون بياناتك متاحة في مركز Hugging Face، يرجى التواصل عبر فتح مناقشة أو طلب سحب في تبويب المجتمع الخاص بصفحة مجموعة البيانات. شكرًا لمساهمتك في مجتمع تعلم الآلة!

## اقتباس BibTeX

للاستشهاد بمكتبة 🤗 Datasets في أبحاثك، يمكنك استخدام المرجع التالي:

```bibtex
@inproceedings{lhoest-etal-2021-datasets,
    title = "Datasets: A Community Library for Natural Language Processing",
    author = "Lhoest, Quentin  and
      Villanova del Moral, Albert  and
      Jernite, Yacine  and
      Thakur, Abhishek  and
      von Platen, Patrick  and
      Patil, Suraj  and
      Chaumond, Julien  and
      Drame, Mariama  and
      Plu, Julien  and
      Tunstall, Lewis  and
      Davison, Joe  and
      {\v{S}}a{\v{s}}ko, Mario  and
      Chhablani, Gunjan  and
      Malik, Bhavitvya  and
      Brandeis, Simon  and
      Le Scao, Teven  and
      Sanh, Victor  and
      Xu, Canwen  and
      Patry, Nicolas  and
      McMillan-Major, Angelina  and
      Schmid, Philipp  and
      Gugger, Sylvain  and
      Delangue, Cl{\'e}ment  and
      Matussi{\`e}re, Th{\'e}o  and
      Debut, Lysandre  and
      Bekman, Stas  and
      Cistac, Pierric  and
      Goehringer, Thibault  and
      Mustar, Victor  and
      Lagunas, Fran{\c{c}}ois  and
      Rush, Alexander  and
      Wolf, Thomas",
    booktitle = "Proceedings of the 2021 Conference on Empirical Methods in Natural Language Processing: System Demonstrations",
    month = nov,
    year = "2021",
    address = "Online and Punta Cana, Dominican Republic",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2021.emnlp-demo.21",
    pages = "175--184",
    abstract = "The scale, variety, and quantity of publicly-available NLP datasets has grown rapidly as researchers propose new tasks, larger models, and novel benchmarks. Datasets is a community library for contemporary NLP designed to support this ecosystem. Datasets aims to standardize end-user interfaces, versioning, and documentation, while providing a lightweight front-end that behaves similarly for small datasets as for internet-scale corpora. The design of the library incorporates a distributed, community-driven approach to adding datasets and documenting usage. After a year of development, the library now includes more than 650 unique datasets, has more than 250 contributors, and has helped support a variety of novel cross-dataset research projects and shared tasks. The library is available at https://github.com/huggingface/datasets.",
    eprint={2109.02846},
    archivePrefix={arXiv},
    primaryClass={cs.CL},
}
```

إذا كنت تحتاج إلى الاستشهاد بإصدار محدد من مكتبة 🤗 Datasets لضمان إعادة إنتاج النتائج، يمكنك استخدام DOI الخاص بالإصدار من هذا [القائمة](https://zenodo.org/search?q=conceptrecid:%224817768%22&sort=-version&all_versions=True).

---

# مثال عملي: تطبيق Flask بسيط يستخدم مكتبة 🤗 Datasets
# SQuAD

SQuAD هي مجموعة بيانات شهيرة تستخدم في مهام الأسئلة والإجابات على النصوص (Reading Comprehension).

تحتوي على مقالات نصية (**context paragraphs**)، أسئلة (**questions**) مرتبطة بهذه المقالات، وإجابات صحيحة (**answers**) مأخوذة من النص.

**الهدف:** بناء نموذج يقرأ الفقرة ويجيب عن السؤال بشكل دقيق.

عادةً تتكون كل عينة بيانات من:

- **context:** نص أو فقرة من المقال.
- **question:** سؤال متعلق بالنص.
- **answers:** قائمة بالإجابات الصحيحة (نصوص + مواقعها داخل الفقرة).


### 1. ملف المتطلبات `requirements.txt`

```
Flask
datasets
transformers
```

### 2. كود التطبيق `app.py`

```python
from flask import Flask, render_template_string
from datasets import load_dataset

app = Flask(__name__)

# تحميل مجموعة البيانات مرة واحدة عند تشغيل التطبيق
squad_dataset = load_dataset("squad")

@app.route("/")
def home():
    # الحصول على أول مثال من مجموعة التدريب
    first_example = squad_dataset["train"][0]
    context = first_example["context"]
    question = first_example["question"]
    answer = first_example["answers"]["text"][0] if first_example["answers"]["text"] else "لا توجد إجابة"

    # قالب HTML بسيط لعرض البيانات
    html = """
    <h1>مثال من مجموعة بيانات SQuAD</h1>
    <p><b>السؤال:</b> {{ question }}</p>
    <p><b>النص:</b> {{ context }}</p>
    <p><b>الإجابة:</b> {{ answer }}</p>
    """

    return render_template_string(html, question=question, context=context, answer=answer)


if __name__ == "__main__":
    app.run(debug=True)
```

---

### 3. خطوات التشغيل

1. إنشاء بيئة افتراضية:

```bash
python -m venv venv
source venv/bin/activate   # على لينكس/ماك
venv\Scripts\activate      # على ويندوز
```

2. تثبيت المتطلبات:

```bash
pip install -r requirements.txt
```

3. تشغيل التطبيق:

```bash
python app.py
```

4. افتح المتصفح على الرابط:

```
http://127.0.0.1:5000/
``



<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://huggingface.co/datasets/huggingface/documentation-images/raw/main/datasets-logo-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://huggingface.co/datasets/huggingface/documentation-images/raw/main/datasets-logo-light.svg">
    <img alt="Hugging Face Datasets Library" src="https://huggingface.co/datasets/huggingface/documentation-images/raw/main/datasets-logo-light.svg" width="352" height="59" style="max-width: 100%;">
  </picture>
  <br/>
  <br/>
</p>

<p align="center">
    <a href="https://github.com/huggingface/datasets/actions/workflows/ci.yml?query=branch%3Amain"><img alt="Build" src="https://github.com/huggingface/datasets/actions/workflows/ci.yml/badge.svg?branch=main"></a>
    <a href="https://github.com/huggingface/datasets/blob/main/LICENSE"><img alt="GitHub" src="https://img.shields.io/github/license/huggingface/datasets.svg?color=blue"></a>
    <a href="https://huggingface.co/docs/datasets/index.html"><img alt="Documentation" src="https://img.shields.io/website/http/huggingface.co/docs/datasets/index.html.svg?down_color=red&down_message=offline&up_message=online"></a>
    <a href="https://github.com/huggingface/datasets/releases"><img alt="GitHub release" src="https://img.shields.io/github/release/huggingface/datasets.svg"></a>
    <a href="https://huggingface.co/datasets/"><img alt="Number of datasets" src="https://img.shields.io/endpoint?url=https://huggingface.co/api/shields/datasets&color=brightgreen"></a>
    <a href="CODE_OF_CONDUCT.md"><img alt="Contributor Covenant" src="https://img.shields.io/badge/Contributor%20Covenant-2.0-4baaaa.svg"></a>
    <a href="https://zenodo.org/badge/latestdoi/250213286"><img src="https://zenodo.org/badge/250213286.svg" alt="DOI"></a>
</p>

🤗 Datasets is a lightweight library providing **two** main features:

- **one-line dataloaders for many public datasets**: one-liners to download and pre-process any of the ![number of datasets](https://img.shields.io/endpoint?url=https://huggingface.co/api/shields/datasets&color=brightgreen) major public datasets (image datasets, audio datasets, text datasets in 467 languages and dialects, etc.) provided on the [HuggingFace Datasets Hub](https://huggingface.co/datasets). With a simple command like `squad_dataset = load_dataset("squad")`, get any of these datasets ready to use in a dataloader for training/evaluating a ML model (Numpy/Pandas/PyTorch/TensorFlow/JAX),
- **efficient data pre-processing**: simple, fast and reproducible data pre-processing for the public datasets as well as your own local datasets in CSV, JSON, text, PNG, JPEG, WAV, MP3, Parquet, etc. With simple commands like `processed_dataset = dataset.map(process_example)`, efficiently prepare the dataset for inspection and ML model evaluation and training.

[🎓 **Documentation**](https://huggingface.co/docs/datasets/) [🔎 **Find a dataset in the Hub**](https://huggingface.co/datasets) [🌟 **Share a dataset on the Hub**](https://huggingface.co/docs/datasets/share)

<h3 align="center">
    <a href="https://hf.co/course"><img src="https://raw.githubusercontent.com/huggingface/datasets/main/docs/source/imgs/course_banner.png"></a>
</h3>

🤗 Datasets is designed to let the community easily add and share new datasets.

🤗 Datasets has many additional interesting features:

- Thrive on large datasets: 🤗 Datasets naturally frees the user from RAM memory limitation, all datasets are memory-mapped using an efficient zero-serialization cost backend (Apache Arrow).
- Smart caching: never wait for your data to process several times.
- Lightweight and fast with a transparent and pythonic API (multi-processing/caching/memory-mapping).
- Built-in interoperability with NumPy, pandas, PyTorch, TensorFlow 2 and JAX.
- Native support for audio and image data.
- Enable streaming mode to save disk space and start iterating over the dataset immediately.

🤗 Datasets originated from a fork of the awesome [TensorFlow Datasets](https://github.com/tensorflow/datasets) and the HuggingFace team want to deeply thank the TensorFlow Datasets team for building this amazing library. More details on the differences between 🤗 Datasets and `tfds` can be found in the section [Main differences between 🤗 Datasets and `tfds`](#main-differences-between--datasets-and-tfds).

# Installation

## With pip

🤗 Datasets can be installed from PyPi and has to be installed in a virtual environment (venv or conda for instance)

```bash
pip install datasets
```

## With conda

🤗 Datasets can be installed using conda as follows:

```bash
conda install -c huggingface -c conda-forge datasets
```

Follow the installation pages of TensorFlow and PyTorch to see how to install them with conda.

For more details on installation, check the installation page in the documentation: https://huggingface.co/docs/datasets/installation

## Installation to use with PyTorch/TensorFlow/pandas

If you plan to use 🤗 Datasets with PyTorch (1.0+), TensorFlow (2.2+) or pandas, you should also install PyTorch, TensorFlow or pandas.

For more details on using the library with NumPy, pandas, PyTorch or TensorFlow, check the quick start page in the documentation: https://huggingface.co/docs/datasets/quickstart

# Usage

🤗 Datasets is made to be very simple to use - the API is centered around a single function, `datasets.load_dataset(dataset_name, **kwargs)`, that instantiates a dataset.

This library can be used for text/image/audio/etc. datasets. Here is an example to load a text dataset:

Here is a quick example:

```python
from datasets import load_dataset

# Print all the available datasets
from huggingface_hub import list_datasets
print([dataset.id for dataset in list_datasets()])

# Load a dataset and print the first example in the training set
squad_dataset = load_dataset('squad')
print(squad_dataset['train'][0])

# Process the dataset - add a column with the length of the context texts
dataset_with_length = squad_dataset.map(lambda x: {"length": len(x["context"])})

# Process the dataset - tokenize the context texts (using a tokenizer from the 🤗 Transformers library)
from transformers import AutoTokenizer
tokenizer = AutoTokenizer.from_pretrained('bert-base-cased')

tokenized_dataset = squad_dataset.map(lambda x: tokenizer(x['context']), batched=True)
```

If your dataset is bigger than your disk or if you don't want to wait to download the data, you can use streaming:

```python
# If you want to use the dataset immediately and efficiently stream the data as you iterate over the dataset
image_dataset = load_dataset('cifar100', streaming=True)
for example in image_dataset["train"]:
    break
```

For more details on using the library, check the quick start page in the documentation: https://huggingface.co/docs/datasets/quickstart and the specific pages on:

- Loading a dataset: https://huggingface.co/docs/datasets/loading
- What's in a Dataset: https://huggingface.co/docs/datasets/access
- Processing data with 🤗 Datasets: https://huggingface.co/docs/datasets/process
    - Processing audio data: https://huggingface.co/docs/datasets/audio_process
    - Processing image data: https://huggingface.co/docs/datasets/image_process
    - Processing text data: https://huggingface.co/docs/datasets/nlp_process
- Streaming a dataset: https://huggingface.co/docs/datasets/stream
- Writing your own dataset loading script: https://huggingface.co/docs/datasets/dataset_script
- etc.

# Add a new dataset to the Hub

We have a very detailed step-by-step guide to add a new dataset to the ![number of datasets](https://img.shields.io/endpoint?url=https://huggingface.co/api/shields/datasets&color=brightgreen) datasets already provided on the [HuggingFace Datasets Hub](https://huggingface.co/datasets).

You can find:
- [how to upload a dataset to the Hub using your web browser or Python](https://huggingface.co/docs/datasets/upload_dataset) and also
- [how to upload it using Git](https://huggingface.co/docs/datasets/share).

# Main differences between 🤗 Datasets and `tfds`

If you are familiar with the great TensorFlow Datasets, here are the main differences between 🤗 Datasets and `tfds`:

- the scripts in 🤗 Datasets are not provided within the library but are queried, downloaded/cached and dynamically loaded upon request
- the backend serialization of 🤗 Datasets is based on [Apache Arrow](https://arrow.apache.org/) instead of TF Records and leverage python dataclasses for info and features with some diverging features (we mostly don't do encoding and store the raw data as much as possible in the backend serialization cache).
- the user-facing dataset object of 🤗 Datasets is not a `tf.data.Dataset` but a built-in framework-agnostic dataset class with methods inspired by what we like in `tf.data` (like a `map()` method). It basically wraps a memory-mapped Arrow table cache.

# Disclaimers

🤗 Datasets may run Python code defined by the dataset authors to parse certain data formats or structures. For security reasons, we ask users to:
- check the dataset scripts they're going to run beforehand and
- pin the `revision` of the repositories they use.

If you're a dataset owner and wish to update any part of it (description, citation, license, etc.), or do not want your dataset to be included in the Hugging Face Hub, please get in touch by opening a discussion or a pull request in the Community tab of the dataset page. Thanks for your contribution to the ML community!

## BibTeX

If you want to cite our 🤗 Datasets library, you can use our [paper](https://arxiv.org/abs/2109.02846):

```bibtex
@inproceedings{lhoest-etal-2021-datasets,
    title = "Datasets: A Community Library for Natural Language Processing",
    author = "Lhoest, Quentin  and
      Villanova del Moral, Albert  and
      Jernite, Yacine  and
      Thakur, Abhishek  and
      von Platen, Patrick  and
      Patil, Suraj  and
      Chaumond, Julien  and
      Drame, Mariama  and
      Plu, Julien  and
      Tunstall, Lewis  and
      Davison, Joe  and
      {\v{S}}a{\v{s}}ko, Mario  and
      Chhablani, Gunjan  and
      Malik, Bhavitvya  and
      Brandeis, Simon  and
      Le Scao, Teven  and
      Sanh, Victor  and
      Xu, Canwen  and
      Patry, Nicolas  and
      McMillan-Major, Angelina  and
      Schmid, Philipp  and
      Gugger, Sylvain  and
      Delangue, Cl{\'e}ment  and
      Matussi{\`e}re, Th{\'e}o  and
      Debut, Lysandre  and
      Bekman, Stas  and
      Cistac, Pierric  and
      Goehringer, Thibault  and
      Mustar, Victor  and
      Lagunas, Fran{\c{c}}ois  and
      Rush, Alexander  and
      Wolf, Thomas",
    booktitle = "Proceedings of the 2021 Conference on Empirical Methods in Natural Language Processing: System Demonstrations",
    month = nov,
    year = "2021",
    address = "Online and Punta Cana, Dominican Republic",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2021.emnlp-demo.21",
    pages = "175--184",
    abstract = "The scale, variety, and quantity of publicly-available NLP datasets has grown rapidly as researchers propose new tasks, larger models, and novel benchmarks. Datasets is a community library for contemporary NLP designed to support this ecosystem. Datasets aims to standardize end-user interfaces, versioning, and documentation, while providing a lightweight front-end that behaves similarly for small datasets as for internet-scale corpora. The design of the library incorporates a distributed, community-driven approach to adding datasets and documenting usage. After a year of development, the library now includes more than 650 unique datasets, has more than 250 contributors, and has helped support a variety of novel cross-dataset research projects and shared tasks. The library is available at https://github.com/huggingface/datasets.",
    eprint={2109.02846},
    archivePrefix={arXiv},
    primaryClass={cs.CL},
}
```

If you need to cite a specific version of our 🤗 Datasets library for reproducibility, you can use the corresponding version Zenodo DOI from this [list](https://zenodo.org/search?q=conceptrecid:%224817768%22&sort=-version&all_versions=True).
