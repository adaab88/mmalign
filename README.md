# mmalign

**检查多模态提示里的文字与图像描述是否对应。**

`mmalign` —— 比对提示中引用的图像元素与实际图像，标出指代错位

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`mmalign.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install adaab88-mmalign
```

装完直接用命令名调用：

```bash
mmalign --help
```

也可以不用安装，直接把 `mmalign.py` 拷走用——它只依赖标准库。

## 为什么需要它

「图里有狗，提示里说猫」这类错位工具要能抓

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 多模态提示对齐 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python mmalign.py --file input.txt
python mmalign.py --text "示例内容"
python mmalign.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 一致性靠字面差异判定，语义等价但写法不同会误报。
- 不解析跨文档的引用关系。

## 跑测试

```bash
python test_mmalign.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/adaab88/mmalign>

---

## 关于作者

adaab88 做多模态提示对齐相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://adaab88.github.io>
- 仓库：<https://github.com/adaab88/mmalign>

## 许可

MIT，见 [LICENSE](LICENSE)。
