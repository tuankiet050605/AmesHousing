# Project: Sức mạnh của Data Preparation qua Data Storytelling

## Nhóm thực hiện

| STT | Họ và tên | Mã sinh viên |
|-----|------------|--------------|
| 1 | **Doãn Quốc Bảo** | 11230519 |
| 2 | **Nguyễn Thị Mai Anh** | 11230511 |
| 3 | **Hà Quang Minh** | 11230566 |
| 4 | **Nguyễn Trần Tuấn Kiệt** | 11230554 |
| 5 | **Trịnh Minh Hiếu** | 11230536 |

---

## Giới thiệu

## Đề tài
**Sử dụng các kỹ thuật Data Storytelling để chứng minh và khẳng định vai trò quan trọng của Data Preparation (chuẩn bị dữ liệu) trong một dự án Machine Learning.**

Dự án minh họa toàn bộ quy trình **phân tích, làm sạch, xử lý và chuẩn bị dữ liệu**, **so sánh tác động của cac kỹ thuật sử lý dữ liệu** trên bộ dữ liệu **Ames Housing** – dùng để dự đoán giá nhà ở Ames, Iowa.  
Thông qua **Data Storytelling**, nhóm thể hiện rõ **sự khác biệt về insight và kết quả mô hình** giữa dữ liệu thô và dữ liệu đã được chuẩn bị kỹ lưỡng thông qua những phương pháp sử lý dữ liệu.

---

## Bộ dữ liệu

- **Tên:** Ames Housing Dataset  
- **Nguồn:** Kaggle – House Prices: Advanced Regression Techniques  
- **Số dòng:** ~2930 | **Số cột:** ~82 | **Target:** `SalePrice` (USD)

---

## Cấu trúc dự án

| Notebook | Mô tả |
|-----------|-------|
| **phân tích và xử lý dữ liệu.ipynb** | Phần **EDA** – khám phá dữ liệu, trực quan hóa phân phối, phát hiện outlier, phân tích tương quan, log-transform `SalePrice`. |
| **chart for comparison and report.ipynb** | **Notebook so sánh từng bước** (*before/after*) của quy trình **Data Preparation**. Mỗi phần đều trình bày song song kết quả **trước** và **sau** xử lý: làm sạch dữ liệu thiếu, mã hóa biến phân loại, chuẩn hóa, tạo biến `TotalSF`, và **so sánh tác động** lên trực quan hóa/insights và kết quả mô hình đơn giản. |

> Ghi chú: **chart for comparison and report.ipynb** được thiết kế để **minh họa tác động của từng kỹ thuật xử lý** — không chỉ đưa ra pipeline cuối cùng, mà còn chỉ ra **từng bước cải thiện** so với dữ liệu ban đầu. Ngoài ra **chart for comparison and report.ipynb** còn dùng để vẽ một số biểu đồ dùng cho phần trình bày về dự án (slide/report).

---

## Kết quả đánh giá

Nhóm tiến hành đánh giá mô hình **Linear Regression** trên hai tập dữ liệu:

| Phiên bản dữ liệu | R² (↑) | MAE (↓) | RMSE (↓) | Nhận xét |
|--------------------|--------|----------|-----------|-----------|
| **Raw (chưa xử lý)** | 0.85 | 20,834.50 | 32,940.98 | Mô hình học được xu hướng tổng thể nhưng sai số cao do dữ liệu chưa làm sạch, còn outlier và lệch phân phối. |
| **Clean (đã xử lý)** | **0.91** | **9,640.36** | **22,775.76** | Sau khi xử lý (loại outlier, log-transform, imputation, scaling, feature engineering), độ chính xác mô hình tăng rõ rệt, sai số giảm hơn **30%**. |

### Nhận định
- Việc **chuẩn bị dữ liệu đúng cách** giúp cải thiện đáng kể hiệu năng mô hình.  
- Sự khác biệt giữa “Raw” và “Clean” thể hiện rõ qua các chỉ số:
  - **R² tăng từ 0.85 → 0.91** (mô hình giải thích được nhiều phương sai hơn).  
  - **MAE và RMSE giảm mạnh** → mô hình dự đoán giá nhà sát thực tế hơn.  
- Đây chính là minh chứng cụ thể cho **sức mạnh của Data Preparation** – làm sạch, biến đổi và chuẩn hóa dữ liệu là bước quan trọng nhất trong chuỗi Machine Learning.

---

> Ghi chú: *Kết quả được trích xuất trực tiếp từ notebook `Data_Processing.ipynb` trong phần so sánh dữ liệu thô và dữ liệu sau xử lý.*

---

## Công nghệ sử dụng

Dự án được xây dựng hoàn toàn bằng **Python** trong môi trường **Jupyter Notebook**, kết hợp các thư viện phổ biến cho phân tích và xử lý dữ liệu.

### Ngôn ngữ & Môi trường
- **Python 3.8+** — ngôn ngữ chính cho xử lý dữ liệu và kể chuyện dữ liệu (Data Storytelling).  
- **Jupyter Notebook** — môi trường phát triển tương tác, giúp trình bày mã, biểu đồ và diễn giải trong cùng một nơi.

---

### Thư viện & Công cụ chính
| Thư viện | Chức năng |
|-----------|------------|
| **pandas** | Xử lý, làm sạch, tổng hợp và thao tác dữ liệu dạng bảng. |
| **numpy** | Xử lý mảng số học, log-transform và các phép tính thống kê. |
| **matplotlib** | Vẽ biểu đồ cơ bản: histogram, scatter plot, boxplot, line chart. |
| **seaborn** | Trực quan hóa dữ liệu nâng cao: heatmap, pairplot, biểu đồ tương quan. |
| **scikit-learn** | Tiền xử lý và mô hình hóa dữ liệu: `SimpleImputer`, `StandardScaler`, `OneHotEncoder`, `Pipeline`, `train_test_split`, `LinearRegression`. |

---

### Kỹ thuật Data Preparation
- Xử lý giá trị thiếu (`SimpleImputer`, `fillna`)  
- Mã hóa biến phân loại (`OneHotEncoder`, `get_dummies`)  
- Chuẩn hóa dữ liệu (`StandardScaler`)  
- Tạo đặc trưng mới (`TotalSF` = tổng diện tích sàn)  
- Log-transform biến mục tiêu (`np.log1p(SalePrice)`)  

---

### Công cụ hỗ trợ & Trình bày
- **GitHub** — lưu trữ mã nguồn và notebook.  
- **Markdown / README.md** — viết tài liệu chuyên nghiệp cho dự án.  
- **PowerPoint / Google Slides** — dùng cho phần trình bày *Data Storytelling*.

---

## Hướng dẫn chạy

### Chuẩn bị môi trường
- **Python 3.8+**
- **Git** và **pip** đã được cài sẵn
- **Jupyter Notebook** (hoặc **JupyterLab**, **VSCode** với Python extension)

---

### Tải mã nguồn từ GitHub
```bash
git clone https://github.com/tuankiet050605/AmesHousing
cd AmesHousing
```

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
# hoặc
pip install -r requirements.txt
```
---

### Chạy notebook
```bash
jupyter notebook
```
Mở:  
- `phân tích và xử lý dữ liệu.ipynb`  
- `Data_Processing.ipynb`

---

## Giấy phép

- **Nguồn dữ liệu:** [Ames Housing Dataset – Kaggle](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data)  
- **Giấy phép dữ liệu:** CC0 Public Domain — bạn có thể tự do sử dụng, chia sẻ và phân tích.

