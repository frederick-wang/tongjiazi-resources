
# 📜 通假字资源库

通假字资源库是一个专为古汉语通假字研究和应用而创建的开源项目。它由通假字标注语料库、通假字知识库以及通假字识别评测集三部分组成。

## 📝 引用

如果您在研究中使用了此项目，请引用以下论文:

```
王兆基, 张诗睿, 张学涛, 胡韧奋*. 古汉语通假字资源库的构建及应用研究. 第二十二届中国计算语言学大会 (CCL 2023)
```

## 🌐 在线浏览

您可以访问 [https://tjz.zhaoji.ac.cn/](https://tjz.zhaoji.ac.cn/) 在线浏览通假字资源库。

## 📥 数据下载

为了防止爬虫爬取，我们将数据压缩成了 `zip` 格式，解压密码均为 `BEIJING_NORMAL_UNIVERSITY`。

## 📂 目录结构

- `corpus`: 通假字标注语料库
- `knowledge_base`: 通假字知识库
- `evaluation`: 通假字识别评测集

## 🗂 文件格式

### 📖 通假字标注语料库

只有一个文件 `corpus.jsonl`，使用 `jsonl` 格式存储，每一行是一个 `json` 对象，包含以下字段：

- `语料ID`: 语料的唯一标识符，从 1 开始递增；
- `语料文本`: 语料的文本内容；
- `标注位置`: 通假字的标注位置，从 0 开始计数；
- `通假字字头`: 通假字的字头，参见[《汉语大词典》凡例说明](https://hd.cnki.net/kxhd/Introduce/HDFanLi)；
- `正字字头`: 正字的字头，参见[《汉语大词典》凡例说明](https://hd.cnki.net/kxhd/Introduce/HDFanLi)；
- `出处`: 语料的出处；
- `时代`: 语料的时代；
- `释义`: 通假字的释义；
- `拼音`: 通假字的拼音；
- `注音`: 通假字的注音；
- `古音`: 通假字的古音。

### 🗃️ 通假字知识库

包含 `nodes.jsonl`、`tongjia_links.jsonl`、`xingsheng_links.jsonl`、`yuliao.jsonl` 四个文件，使用 `jsonl` 格式存储，每一行是一个 `json` 对象。

`nodes.jsonl` 中 `json` 对象包含以下字段：

- `节点ID`: 节点的唯一标识符，从 0 开始递增；
- `字`: 节点的字；
- `部首`: 节点的部首；
- `部件`: 节点的部件；
- `结构`: 节点的结构。

`tongjia_links.jsonl` 中 `json` 对象包含以下字段：

- `通假关系ID`: 通假关系的唯一标识符，从 0 开始递增；
- `通假字`: 通假字的字形；
- `正字`: 正字的字形；
- `拼音`: 通假字的拼音；
- `注音`: 通假字的注音；
- `古音`: 通假字的古音；
- `释义`: 通假字的释义；
- `关联语料ID集合`: 通假字关系关联的语料的ID集合。

`xingheng_links.jsonl` 中 `json` 对象包含以下字段：

- `形声关系ID`: 形声关系的唯一标识符，从 0 开始递增；
- `形声字`: 形声字的字形；
- `声旁`: 声旁的字形；

`yuliao.jsonl` 中 `json` 对象包含以下字段：

- `语料ID`: 语料的唯一标识符，从 0 开始递增；
- `语料`: 语料的文本内容；
- `出处`: 语料的出处；
- `时代`: 语料的时代；
- `来源`: 语料的来源。

### 🎯 通假字识别评测集

包含 `based_detection.jsonl`、`based_recognition.jsonl`、`extended_detection.jsonl`、`extended_recognition.jsonl` 四个文件，使用 `jsonl` 格式存储，每一行是一个 `json` 对象。

`based_detection.jsonl` 中 `json` 对象包含以下字段：

- `input`: 通假字检测任务基础版的输入，为一个 `object`，包含 `sentence` 字段，为待检测的句子；
- `output`: 通假字检测任务基础版的输出，为一个 `array`，包含所有通假字的位置。

`based_recognition.jsonl` 中 `json` 对象包含以下字段：

- `input`: 正字识别任务基础版的输入，为一个 `object`，包含 `sentence` 字段，为待识别的句子，`pos` 字段，为待识别的通假字的位置；
- `output`: 正字识别任务基础版的输出，为一个 `string`，为识别出的正字。

`extended_detection.jsonl` 中 `json` 对象包含以下字段：

- `input`: 通假字检测任务拓展版的输入，为一个 `object`，包含 `sentence` 字段，为待检测的句子；
- `output`: 通假字检测任务拓展版的输出，为一个 `array`，包含所有通假字的位置。

`extended_recognition.jsonl` 中 `json` 对象包含以下字段：

- `input`: 正字识别任务拓展版的输入，为一个 `object`，包含 `sentence` 字段，为待识别的句子，`pos` 字段，为待识别的通假字的位置；
- `output`: 正字识别任务拓展版的输出，为一个 `string`，为识别出的正字。

## 💡 贡献

如果发现数据有误，或者有任何建议，欢迎提交 [issue](https://github.com/frederick-wang/tongjiazi-resources/issues)。

## 📄 许可

此项目采用 MIT 许可证。详情请参考 [LICENSE](./LICENSE) 文件。
