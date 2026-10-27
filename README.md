# privcheck

**检查数据处理是否满足隐私要求。**

`privcheck` —— 逐项核对数据使用、留存与同意状态，标出不合规项

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`privcheck.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install nothingraf-privcheck
```

装完直接用命令名调用：

```bash
privcheck --help
```

也可以不用安装，直接把 `privcheck.py` 拷走用——它只依赖标准库。

## 为什么需要它

按可核对的条款判定，不做模糊的「看起来还好」

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 隐私合规检查 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python privcheck.py --file input.txt
python privcheck.py --text "示例内容"
python privcheck.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 类型推断基于 AST，动态构造的返回值会标为无法判定。
- 不校验业务语义，只校验结构。

## 跑测试

```bash
python test_privcheck.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/nothingraf/privcheck>

---

## 关于作者

nothingraf 做隐私合规检查相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://nothingraf.github.io>
- 仓库：<https://github.com/nothingraf/privcheck>

## 许可

MIT，见 [LICENSE](LICENSE)。
