# 华为鸿蒙，小米澎湃，苹果ios字体在线调用库
## 食用方式
### 得到调用链接
1. 在[项目文件](https://github.com/fengjiayou/HarmonyOS-HyperOS-iOS-Font-Integration/tree/main/HarmonyOS%20Sans)中找到想要用的字体并复制路径
（如：` HarmonyOS Sans/HarmonyOS_Sans_Condensed_Italic/HarmonyOS_Sans_Condensed_Black_Italic.ttf ` ） ![eg-0](https://fengjiayou.github.io/HarmonyOS-HyperOS-iOS-Font-Integration/README/0.png)

2. 访问[https://fengjiayou.github.io/HarmonyOS-HyperOS-iOS-Font-Integration/index.html](https://fengjiayou.github.io/HarmonyOS-HyperOS-iOS-Font-Integration/index.html)在对话框中输入路径生成链接
（如: 输入 ` HarmonyOS Sans/HarmonyOS_Sans_Condensed_Italic/HarmonyOS_Sans_Condensed_Black_Italic.ttf ` 输出 ` https://fengjiayou.github.io/HarmonyOS-HyperOS-iOS-Font-Integration/HarmonyOS Sans/HarmonyOS_Sans_Condensed_Italic/HarmonyOS_Sans_Condensed_Black_Italic.ttf `）

### 调用

#### HTML/CSS标准调用
```html
<!DOCTYPE html>
<html>
<head>
    <style>
        /* 字体定义 */
        @font-face {
            font-family: 'HarmonyOS-Condensed-Black-Italic';
            src: url('https://fengjiayou.github.io/HarmonyOS-HyperOS-iOS-Font-Integration/HarmonyOS%20Sans/HarmonyOS_Sans_Condensed_Italic/HarmonyOS_Sans_Condensed_Black_Italic.ttf')
                 format('truetype');
            font-weight: 900;
            font-style: italic;
            font-display: swap;
        }

        /* 字体应用 */
        .font-demo {
            font-family: 'HarmonyOS-Condensed-Black-Italic', sans-serif;
            font-size: 24px;
        }
    </style>
</head>
<body>
    <p class="font-demo">HarmonyOS Sans字体演示：123ABC测试文本</p>
</body>
</html>
```
#### JavaScript动态加载
```javascript
const loadFont = async () => {
    try {
        const font = new FontFace(
            'HarmonyOS-Condensed-Black-Italic',
            'url(https://fengjiayou.github.io/HarmonyOS-HyperOS-iOS-Font-Integration/HarmonyOS%20Sans/HarmonyOS_Sans_Condensed_Italic/HarmonyOS_Sans_Condensed_Black_Italic.ttf)'
        );
        
        const loadedFont = await font.load();
        document.fonts.add(loadedFont);
        console.log('🟢 字体加载成功');
    } catch (error) {
        console.error('🔴 字体加载失败:', error);
    }
};

loadFont();
```
#### 技术规范
##### 路径处理规范
| 原始字符 | 转换后字符 | 示例 |
| :-----: | :----: | :----: |
| 空格 | %20 | ` HarmonyOS%20Sans ` |
| 中文 | URL编码 | ` %E4%B8%AD%E6%96%87 ` |
##### 性能优化建议
```css
@font-face {
    font-display: swap;          /* 无布局偏移加载策略 */
    unicode-range: U+000-5FF;    /* 按需加载拉丁/中文基础字符集 */
    size-adjust: 98%;            /* 微调字体渲染尺寸 */
}
```
## 免责声明

本《免责声明》（以下简称“声明”）适用于通过本平台/工具（以下简称“服务”）调用**华为鸿蒙系统字体**、**小米澎湃OS字体**、**苹果iOS系统字体**（以下简称“相关字体”）的所有用户。请在使用前仔细阅读并同意以下条款：

---

### 一、版权与知识产权声明

1. **字体所有权**  
   华为鸿蒙字体、小米澎湃OS字体、苹果iOS系统字体分别为**华为技术有限公司**、**小米集团**、**苹果公司（Apple Inc.）**的独立知识产权。本服务仅提供技术调用接口，**不拥有相关字体的任何著作权、商标权或其他合法权益**。

2. **合法使用义务**  
   用户须自行确保调用字体的行为符合相关字体所有者的官方授权条款。**禁止将字体用于以下用途**：  
   - 商业用途  
   - 二次分发或修改  
   - 侵犯第三方权利的行为  
   违反上述条款的责任由用户自行承担。

---

### 二、免责条款

1. **服务性质**  
   本服务为技术中立工具，不参与用户实际使用场景的合法性审查。**不对以下行为承担责任**：  
   - 字体在商业设计、出版物、广告等场景的应用  
   - 因字体使用引发的法律争议  

2. **风险自担**  
   因使用本服务或相关字体导致的以下后果，**均由用户自行承担**：  
   - 版权纠纷、法律争议  
   - 经济损失（包括但不限于索赔、诉讼、行政处罚）  

3. **服务稳定性**  
   本服务不保证：  
   - 字体调用的持续可用性  
   - 字体文件的完整性或准确性  
   因技术故障、政策调整、第三方限制导致的中断或终止，**不承担赔偿责任**。

---

### 三、用户责任

1. **遵守授权协议**  
   用户须自行查阅并严格遵守以下条款：  
   - 华为、小米、苹果官方发布的字体使用协议  
   - 商业用途需直接联系权利方获取授权  

2. **数据与隐私**  
   用户应确保操作符合以下法律法规：  
   - 《中华人民共和国网络安全法》  
   - 《中华人民共和国个人信息保护法》  

---

### 四、其他条款

1. **声明修改权**  
   本服务保留随时更新或修改本声明的权利，修改后的声明自公布之日起生效。

2. **法律适用**  
   本声明的解释、执行及争议解决均依据**中华人民共和国法律**。如发生纠纷，按以下顺序处理：  
   - 优先通过友好协商解决  
   - 协商不成时，提交服务提供方所在地有管辖权的法院诉讼解决  

---

**用户确认**  
一旦使用本服务，即视为已充分阅读、理解并同意本声明的全部内容。如不同意，请立即停止使用。

