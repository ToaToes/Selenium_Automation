1. 验证输入
用途: 确保用户输入符合特定格式，比如电子邮件、电话号码等。
示例: 验证电子邮件格式的正则表达式。
```
regex
Copy code
^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$
```
3. 从文本中提取信息
用途: 从字符串中提取特定模式的数据，如提取日志文件中的错误信息。
示例: 提取IP地址的正则表达式。
```
regex
Copy code
\b(?:\d{1,3}\.){3}\d{1,3}\b
```
4. 替换文本
用途: 在文本中进行替换操作，比如将所有空格替换为下划线。
示例: 替换字符串中的所有空格。
```
python
Copy code
import re

text = "Hello World"
result = re.sub(r'\s+', '_', text)  # 结果: "Hello_World"
```
4. 条件测试
用途: 在自动化测试中，条件验证某些字段或响应是否符合预期。
示例: 验证API响应中是否包含特定格式的数据。
```
python
Copy code
import re

response = '{"email": "test@example.com"}'
assert re.search(r'"email":\s*".+@.+\..+"', response)
```
5. 分割字符串
用途: 按照特定模式分割字符串。
示例: 按照逗号分割字符串。
```
python
Copy code
import re

text = "apple,banana,orange"
fruits = re.split(r',\s*', text)  # 结果: ['apple', 'banana', 'orange']
```

使用正则表达式的工具和框架

Python: 使用re模块进行正则表达式操作。
JavaScript: 使用RegExp对象。
Java: 使用java.util.regex包。
Selenium: 在自动化测试中，可以用正则表达式匹配网页元素的属性或文本内容。
