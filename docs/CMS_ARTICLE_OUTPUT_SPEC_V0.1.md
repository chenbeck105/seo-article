# CMS Article Output Spec v0.1

> 目的：讓 SEO 文章可以直接進入 A-Type CMS，減少人工重新整理。

## 1. 每篇文章輸出必須包含

### 1.1 CMS 基本欄位

- Collection
- Content Type
- Article Title
- Slug
- Excerpt
- Category
- Tags
- Markdown Body
- Cover Image
- Cover Alt Text

### 1.2 SEO 欄位

- SEO Title
- Meta Description

### 1.3 圖片相關

- Cover Image Prompt
- Inline Image Suggestions
- Inline Image Prompt
- Alt Text
- 建議插入位置

---

## 2. SEO Title 是什麼

SEO Title 是搜尋引擎結果頁通常優先使用的頁面標題訊號。

它可以與文章 H1 相同，也可以略作調整。

建議原則：

- 包含 Primary Keyword
- 說清楚頁面內容
- 不堆砌 Keyword
- 不使用誇張承諾
- 盡量讓重要資訊在前段

範例：

```text
文章標題：
移工中文要學到什麼程度？從工作溝通到職前訓練一次看懂

SEO Title：
移工中文要學到什麼程度？工作溝通、華語能力與職前訓練指南
```

---

## 3. Meta Description 是什麼

Meta Description 是搜尋結果中常見的摘要描述來源之一。

主要目的不是直接堆 Keyword，而是：

- 幫助搜尋者快速判斷內容是否符合需求
- 提升點擊意願
- 說清楚文章會回答什麼

建議內容：

```text
主要問題 + 文章涵蓋範圍 + 明確價值
```

避免：

- 重複 SEO Title
- 塞滿 Keyword
- 無法驗證的誇張說法

---

## 4. Excerpt 與 Meta Description 不完全相同

### Excerpt

給網站列表頁、文章卡片、站內預覽使用。

### Meta Description

主要為搜尋結果與 SEO Metadata 使用。

兩者可以相似，但不應強制完全相同。

---

## 5. Tags

Tags 應來自文章實際涵蓋的主題。

建議：

- 3–8 個
- 不要把所有 Long-tail Keyword 都塞進 Tags
- 優先使用可形成站內 Topic Cluster 的穩定詞

範例：

```text
移工教育, 移工中文, 華語學習, 職前訓練, 印尼人才
```

---

## 6. Markdown Body 規格

文章正文以 Markdown 輸出。

### 標題

```markdown
## H2

### H3
```

文章 H1 通常由 CMS 的「文章標題」欄位處理，正文不重複放 H1。

### 表格

```markdown
| 比較項目 | A | B |
|---|---|---|
| 成本 | ... | ... |
| 適用情境 | ... | ... |
```

### 清單

```markdown
- 項目一
- 項目二
- 項目三
```

### 連結

```markdown
[連結文字](https://example.com)
```

### 圖片

若 CMS 支援 Markdown 圖片：

```markdown
![Alt Text](IMAGE_URL)
```

若圖片尚未產生，文章輸出時用明確 placeholder：

```markdown
<!-- IMAGE: 移工職前華語課程情境圖 -->
```

並在文末的 Image Plan 提供 prompt。

---

## 7. Cover Image

每篇文章必須額外提供：

- Cover concept
- Cover image prompt
- Cover alt text

Cover 應服務文章主題，不是純裝飾。

### Cover Prompt Template

```text
Create a clean editorial hero image for an article about [TOPIC].
Scene: [SCENE].
Subjects: [SUBJECTS].
Environment: [ENVIRONMENT].
Visual tone: credible, informative, modern, natural.
Composition: editorial website cover, clear focal point, enough negative space for responsive cropping.
Avoid: embedded text, logos, watermarks, exaggerated advertising style.
Aspect ratio: [CMS COVER RATIO].
```

---

## 8. Inline Images

不是每篇文章都強制插圖。

只有在圖片能增加理解時才使用，例如：

- 流程
- 比較
- 空間 / 安裝示意
- 操作步驟
- 情境說明
- 概念解釋

### Inline Image Plan

每張圖片需提供：

```text
建議位置：
目的：
圖像類型：
Alt Text：
Prompt：
```

### Inline Prompt Template

```text
Create an editorial explanatory image for a section about [SECTION TOPIC].
Show [KEY OBJECTS / ACTION].
The image should help readers understand [LEARNING GOAL].
Style: realistic or clean editorial illustration, informative rather than promotional.
No text labels unless explicitly requested.
No logo, no watermark.
Aspect ratio: [RATIO].
```

如果 AI 生圖不適合精確資訊，例如法規流程、費用表、比較表：
**不要用 AI 圖代替資料本身。**
直接用 Markdown 表格、流程文字或後續人工圖表。

---

## 9. 建議完整輸出格式

```markdown
# CMS Fields

Collection:
Content Type:
Article Title:
Slug:
Excerpt:
Category:
Tags:

SEO Title:
Meta Description:

Cover Alt Text:
Cover Image Prompt:

# Markdown Body

[完整 Markdown 文章]

# Image Plan

## Image 1
位置：
目的：
Alt Text：
Prompt：

## Image 2
位置：
目的：
Alt Text：
Prompt：

# References

1. [來源名稱](URL)
2. [來源名稱](URL)
```

---

## 10. 重要規則

- 文章內容與 SEO metadata 分開輸出
- Markdown 必須可直接複製到 CMS
- 表格一律用 Markdown table
- 圖片 prompt 不要混入文章正文
- 每張圖都要有 Alt Text
- 涉及政策、法規、數字、費用、資格時，References 必須保留
- SEO Title 與 Meta Description 不應取代正文資訊品質
