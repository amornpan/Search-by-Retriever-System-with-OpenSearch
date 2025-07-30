# 🔍 Search by Retriever System with OpenSearch

ระบบค้นหาข้อมูลอัจฉริยะที่ใช้ **OpenSearch** และ **Sentence Transformers** สำหรับการค้นหาข้อมูลด้วย vector embeddings และ semantic similarity

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/your-username/Search-by-Retriever-System-with-OpenSearch/blob/main/opensearch_retriever.ipynb)

## 📋 สารบัญ

- [คุณสมบัติหลัก](#-คุณสมบัติหลัก)
- [เทคโนโลยีที่ใช้](#-เทคโนโลยีที่ใช้)
- [การเริ่มต้นใช้งาน](#-การเริ่มต้นใช้งาน)
- [การใช้งานใน Google Colab](#-การใช้งานใน-google-colab)
- [การใช้งานแบบ Local](#-การใช้งานแบบ-local)
- [โครงสร้างของโปรเจค](#-โครงสร้างของโปรเจค)
- [คำอธิบายแต่ละ Cell](#-คำอธิบายแต่ละ-cell)
- [ตัวอย่างการใช้งาน](#-ตัวอย่างการใช้งาน)
- [การแก้ไขปัญหา](#-การแก้ไขปัญหา)
- [การพัฒนาต่อ](#-การพัฒนาต่อ)

## ✨ คุณสมบัติหลัก

### 🎯 Vector Search System
- **📄 Document Indexing** - เก็บเอกสารพร้อม vector embeddings
- **🔍 Semantic Search** - ค้นหาด้วยความหมายและบริบท  
- **🧠 Multilingual Support** - รองรับภาษาไทยและอังกฤษ
- **⚡ Real-time Indexing** - เพิ่มเอกสารใหม่ได้ทันที

### 📊 การจัดการข้อมูล
- สร้าง vector embeddings จากข้อความ
- จัดเก็บข้อมูลใน OpenSearch
- ค้นหาด้วย cosine similarity
- แสดงผลพร้อมคะแนนความคล้าย

### 🌏 รองรับหลายภาษา
- ใช้ `paraphrase-multilingual-MiniLM-L12-v2` model
- สนับสนุน 50+ ภาษา
- เหมาะสำหรับเนื้อหาภาษาไทย

## 🔧 เทคโนโลยีที่ใช้

| เทคโนโลยี | เวอร์ชัน | วัตถุประสงค์ |
|-----------|---------|-------------|
| **OpenSearch** | Latest | Vector database และ search engine |
| **Sentence Transformers** | Latest | การสร้าง text embeddings |
| **Python** | 3.7+ | ภาษาโปรแกรมหลัก |
| **Jupyter Notebook** | Latest | สภาพแวดล้อมการพัฒนา |

### 📦 Python Libraries
```
opensearch-py==2.4.0      # OpenSearch client
sentence-transformers     # Text embedding models  
pandas                   # Data manipulation
numpy                    # Numerical computations
datasets                 # Dataset handling (ถ้าต้องการ)
```

## 🚀 การเริ่มต้นใช้งาน

### ⚡ วิธีที่ 1: ใช้งานใน Google Colab (แนะนำ)

1. คลิกที่ปุ่ม **"Open in Colab"** ด้านบน
2. ไฟล์ `opensearch_retriever.ipynb` จะเปิดใน Google Colab
3. รันแต่ละ cell ตามลำดับ
4. ไม่ต้องติดตั้งอะไรเพิ่ม - ใช้งานได้ทันที!

### 💻 วิธีที่ 2: ใช้งานแบบ Local

1. **Clone Repository**
```bash
git clone <repository-url>
cd Search-by-Retriever-System-with-OpenSearch
```

2. **สร้าง Virtual Environment**
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
# หรือ
venv\Scripts\activate     # Windows
```

3. **ติดตั้ง Dependencies**
```bash
pip install opensearch-py sentence-transformers pandas numpy datasets
```

4. **เริ่มต้น Jupyter Notebook**
```bash
jupyter notebook opensearch_retriever.ipynb
```

## 📱 การใช้งานใน Google Colab

### ข้อดีของการใช้ Colab:
- ✅ ไม่ต้องติดตั้งอะไรในเครื่อง
- ✅ ใช้ GPU ฟรีสำหรับการประมวลผล
- ✅ แชร์และทำงานร่วมกันได้ง่าย
- ✅ บันทึกอัตโนมัติใน Google Drive

### ขั้นตอนการใช้งาน:
1. เปิดลิงก์ Colab หรืออัปโหลดไฟล์ `.ipynb`
2. ดำเนินการตามคำแนะนำในแต่ละ cell
3. แก้ไข `OPENSEARCH_INDEX` เป็นชื่อของคุณ
4. รัน cell ทีละตัวตามลำดับ

## 🏗️ โครงสร้างของโปรเจค

```
Search-by-Retriever-System-with-OpenSearch/
│
├── opensearch_retriever.ipynb    # Main notebook สำหรับ Google Colab
├── README.md                     # ไฟล์นี้
├── requirements.txt              # Python dependencies (สำหรับ local)
└── data/                         # ตัวอย่างข้อมูล (ถ้ามี)
```

## 📖 คำอธิบายแต่ละ Cell

### Cell 1: Title และ Introduction
- **คำอธิบาย**: แนะนำโปรเจคและการตั้งค่าพื้นฐาน
- **เนื้อหา**: คำอธิบายระบบและ OpenSearch endpoint
- **การใช้งาน**: อ่านเพื่อทำความเข้าใจโปรเจค

### Cell 2: การติดตั้ง Libraries
```python
!pip install opensearch-py sentence-transformers datasets pandas numpy
```
- **คำอธิบาย**: ติดตั้ง libraries ที่จำเป็นทั้งหมด
- **เวลาประมาณ**: 2-3 นาที
- **หมายเหตุ**: ใน Colab จะติดตั้งอัตโนมัติ

### Cell 3: Import Libraries และ Configuration
```python
import json, pandas as pd, numpy as np
from sentence_transformers import SentenceTransformer
from opensearchpy import OpenSearch, RequestsHttpConnection

OPENSEARCH_ENDPOINT = "http://34.101.178.186:9200"
OPENSEARCH_INDEX = "yourname_doc_index"  # ⚠️ เปลี่ยนชื่อ!
```
- **คำอธิบาย**: นำเข้า libraries และกำหนดค่าการเชื่อมต่อ
- **สิ่งที่ต้องแก้**: เปลี่ยน `yourname` เป็นชื่อของคุณ
- **ผลลัพธ์**: แสดง endpoint และ index name

### Cell 4: การเชื่อมต่อ OpenSearch
```python
client = OpenSearch(
    hosts=[{'host': host, 'port': port}],
    http_compress=True,
    use_ssl=False,
    verify_certs=False,
    connection_class=RequestsHttpConnection,
    timeout=60
)
```
- **คำอธิบาย**: สร้าง client เชื่อมต่อกับ OpenSearch
- **การทดสอบ**: เรียก `client.info()` เพื่อทดสอบการเชื่อมต่อ
- **ผลลัพธ์**: ✅ แสดงข้อมูล OpenSearch version

### Cell 5: โหลด Sentence Transformer Model
```python
model = SentenceTransformer('sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2')
```
- **คำอธิบาย**: โหลดโมเดลสำหรับสร้าง text embeddings
- **Model**: Multilingual model รองรับภาษาไทย
- **ขนาด vector**: 384 dimensions
- **เวลา**: 1-2 นาที (ครั้งแรก)

### Cell 6: สร้าง Index Schema
```python
index_mapping = {
    "mappings": {
        "properties": {
            "embedding": {
                "type": "dense_vector",
                "dims": 384,
                "similarity": "cosine"
            }
            # ... other fields
        }
    }
}
```
- **คำอธิบาย**: กำหนดโครงสร้างของ index ใน OpenSearch
- **สำคัญ**: กำหนด vector field สำหรับการค้นหา
- **การทำงาน**: ลบ index เก่า (ถ้ามี) และสร้างใหม่

### Cell 7: เตรียมข้อมูลตัวอย่าง
```python
sample_documents = [
    {
        "id": "doc_001",
        "title": "การเรียนรู้ของเครื่อง (Machine Learning)",
        "content": "การเรียนรู้ของเครื่อง...",
        "category": "AI/ML"
    },
    # ... more documents
]
```
- **คำอธิบาย**: สร้างข้อมูลตัวอย่าง 5 เอกสาร
- **หัวข้อ**: AI/ML, NLP, Database, Web Dev, Cybersecurity
- **ภาษา**: เนื้อหาภาษาไทย

### Cell 8: สร้าง Embeddings และ Index ข้อมูล
```python
def create_document_embedding(title: str, content: str) -> List[float]:
    combined_text = f"{title} {content}"
    embedding = model.encode(combined_text)
    return embedding.tolist()
```
- **คำอธิบาย**: แปลงเอกสารเป็น vector embeddings และเก็บใน OpenSearch
- **กระบวนการ**: 
  1. รวม title + content
  2. สร้าง embedding
  3. Index เข้า OpenSearch
- **ผลลัพธ์**: ✅ Indexed documents พร้อมใช้งาน

### Cell 9: สรุปและขั้นตอนถัดไป
- **คำอธิบาย**: สรุปการทำงานและแนะแนวทางพัฒนาต่อ
- **เนื้อหา**: รายการสิ่งที่สามารถทำต่อได้
- **สถานะ**: ระบบพร้อมใช้งาน

## 🎯 ตัวอย่างการใช้งาน

### การทดสอบหลังจากรัน Notebook

```python
# ทดสอบการค้นหา (เพิ่ม cell ใหม่)
def search_documents(query_text, top_k=3):
    # สร้าง embedding สำหรับ query
    query_embedding = model.encode(query_text).tolist()
    
    # ค้นหาใน OpenSearch
    search_body = {
        "query": {
            "knn": {
                "embedding": {
                    "vector": query_embedding,
                    "k": top_k
                }
            }
        },
        "_source": ["title", "content", "category"]
    }
    
    response = client.search(
        index=OPENSEARCH_INDEX,
        body=search_body
    )
    
    return response['hits']['hits']

# ทดสอบการค้นหา
results = search_documents("ปัญญาประดิษฐ์", top_k=3)
for hit in results:
    doc = hit['_source']
    score = hit['_score']
    print(f"Title: {doc['title']}")
    print(f"Score: {score:.4f}")
    print(f"Category: {doc['category']}")
    print("-" * 50)
```

### การเพิ่มเอกสารใหม่

```python
# เพิ่มเอกสารใหม่
def add_document(doc_id, title, content, category):
    # สร้าง embedding
    embedding = create_document_embedding(title, content)
    
    # เตรียมเอกสาร
    document = {
        "id": doc_id,
        "title": title,
        "content": content,
        "category": category,
        "embedding": embedding,
        "created_at": "2024-01-20T10:00:00Z"
    }
    
    # Index เอกสาร
    response = client.index(
        index=OPENSEARCH_INDEX,
        id=doc_id,
        body=document
    )
    
    return response

# ตัวอย่างการใช้งาน
add_document(
    doc_id="doc_006",
    title="Internet of Things (IoT)",
    content="อินเทอร์เน็ตของสรรพสิ่ง คือเครือข่ายของอุปกรณ์ต่างๆ ที่เชื่อมต่อกันผ่านอินเทอร์เน็ต",
    category="Technology"
)
```

### การดูสถิติและจัดการข้อมูล

```python
# ดูสถิติ index
def get_index_stats():
    try:
        stats = client.indices.stats(index=OPENSEARCH_INDEX)
        doc_count = stats['indices'][OPENSEARCH_INDEX]['total']['docs']['count']
        index_size = stats['indices'][OPENSEARCH_INDEX]['total']['store']['size_in_bytes']
        
        print(f"📊 Index Statistics:")
        print(f"   • Document Count: {doc_count}")
        print(f"   • Index Size: {index_size / 1024:.2f} KB")
        print(f"   • Index Name: {OPENSEARCH_INDEX}")
        
    except Exception as e:
        print(f"❌ Error getting stats: {e}")

# ดูรายการเอกสารทั้งหมด
def list_all_documents():
    try:
        response = client.search(
            index=OPENSEARCH_INDEX,
            body={
                "query": {"match_all": {}},
                "_source": ["id", "title", "category", "created_at"],
                "size": 100
            }
        )
        
        print(f"📄 Documents in Index ({response['hits']['total']['value']} total):")
        for hit in response['hits']['hits']:
            doc = hit['_source']
            print(f"   • {doc['id']}: {doc['title']} ({doc['category']})")
            
    except Exception as e:
        print(f"❌ Error listing documents: {e}")

# เรียกใช้ฟังก์ชัน
get_index_stats()
list_all_documents()
```

## 🐛 การแก้ไขปัญหา

### ปัญหาที่พบบ่อย

#### 1. ไม่สามารถเชื่อมต่อ OpenSearch
```
❌ ConnectionError: [Errno 111] Connection refused
```
**วิธีแก้:**
- ตรวจสอบว่า OpenSearch server ยังทำงานอยู่
- ลองเปลี่ยน endpoint URL
- ตรวจสอบ firewall/network

#### 2. Model โหลดช้าใน Colab
```
Downloading model files...
```
**วิธีแก้:**
- รอให้ download เสร็จ (ครั้งแรกเท่านั้น)
- ใช้ GPU runtime ใน Colab: Runtime → Change runtime type → GPU

#### 3. Index Name ซ้ำกัน
```
resource_already_exists_exception
```
**วิธีแก้:**
- เปลี่ยนชื่อใน `OPENSEARCH_INDEX`
- หรือรัน cell ลบ index ก่อน:
```python
if client.indices.exists(index=OPENSEARCH_INDEX):
    client.indices.delete(index=OPENSEARCH_INDEX)
```

#### 4. Memory Error ใน Colab
**วิธีแก้:**
- ใช้ High-RAM runtime
- ลดขนาด batch ในการประมวลผล
- ปิด cell outputs ที่ไม่จำเป็น

### การตรวจสอบสถานะระบบ

```python
# เพิ่ม cell เพื่อตรวจสอบระบบ
def system_check():
    try:
        # ตรวจสอบ OpenSearch
        info = client.info()
        print(f"✅ OpenSearch OK - Version: {info['version']['number']}")
        
        # ตรวจสอบ Model
        test_embed = model.encode("test")
        print(f"✅ Model OK - Embedding size: {len(test_embed)}")
        
        # ตรวจสอบ Index
        stats = client.indices.stats(index=OPENSEARCH_INDEX)
        doc_count = stats['indices'][OPENSEARCH_INDEX]['total']['docs']['count']
        print(f"✅ Index OK - Documents: {doc_count}")
        
    except Exception as e:
        print(f"❌ Error: {e}")

system_check()
```

## 🔮 การพัฒนาต่อ

### 🎨 UI/UX Enhancements
- [ ] สร้าง Streamlit app สำหรับ web interface
- [ ] เพิ่ม search filters (category, date range)
- [ ] สร้าง search analytics dashboard

### 🧠 AI/ML Improvements  
- [ ] ใช้ larger model เช่น `all-MiniLM-L6-v2`
- [ ] เพิ่ม reranking mechanism
- [ ] implement query expansion

### 📄 Document Processing
- [ ] รองรับ PDF file upload
- [ ] เพิ่ม text chunking สำหรับเอกสารยาว
- [ ] OCR สำหรับไฟล์รูปภาพ

### 🛠️ System Features
- [ ] Batch document processing
- [ ] API endpoint ด้วย FastAPI
- [ ] Monitoring และ logging

### 📱 Integration Options
- [ ] Google Drive integration
- [ ] Slack/Discord bot
- [ ] Chrome extension

## 📞 การติดต่อและการสนับสนุน

- **GitHub Issues**: รายงานปัญหาหรือขอฟีเจอร์ใหม่
- **Discussions**: ถาม-ตอบและแลกเปลี่ยนความคิดเห็น
- **Pull Requests**: ส่งการปรับปรุงโค้ด

## 🙏 Acknowledgments

- **OpenSearch Community** - สำหรับ open-source search engine
- **Sentence Transformers** - สำหรับ pre-trained embedding models  
- **Hugging Face** - สำหรับ model hub และเครื่องมือ ML
- **Google Colab** - สำหรับ free computing resources

## 📄 License

MIT License - ดูไฟล์ [LICENSE](LICENSE) สำหรับรายละเอียด

---

<div align="center">

**🌟 ถ้าคุณชื่นชอบโปรเจคนี้ กรุณาให้ star ⭐ และแชร์ให้เพื่อนๆ ด้วยนะครับ! 🌟**

**📚 เรียนรู้ Vector Search และ Semantic Retrieval ไปพร้อมๆ กัน! 📚**

Made with ❤️ in Thailand 🇹🇭

</div>

---

## 🔗 Quick Links

- 🚀 [เปิดใน Google Colab](https://colab.research.google.com/github/your-username/Search-by-Retriever-System-with-OpenSearch/blob/main/opensearch_retriever.ipynb)
- 📖 [OpenSearch Documentation](https://opensearch.org/docs/)
- 🤗 [Sentence Transformers Documentation](https://www.sbert.net/)
- 💡 [Hugging Face Models](https://huggingface.co/sentence-transformers)
