---
title: "如何：将字符串转换为数字（C# 编程指南） | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "转换 [C#]"
  - "转换 [C#], 字符串转换为 int"
  - "将字符串转换为 int [C#]"
  - "字符串 [C#], 转换为 int"
ms.assetid: 467b9979-86ee-4afd-b734-30299cda91e3
caps.latest.revision: 34
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 34
---
# 如何：将字符串转换为数字（C# 编程指南）
可以使用 <xref:System.Convert> 类中的方法或使用各种数值类型（int、long、float 等）中的 `TryParse` 方法将[字符串](../../../csharp/language-reference/keywords/string.md)转换为数字。  
  
 如果你具有字符串，则调用 `TryParse` 方法（例如 `int.TryParse(“11”)`）会稍微更加高效且简单。  使用 `Convert` 方法对于实现 <xref:System.IConvertible> 的常规对象更有用。  
  
 可以对预期字符串会包含的数值类型（如 <xref:System.Int32?displayProperty=fullName> 类型）使用 `Parse` 或 `TryParse` 方法。  <xref:System.Convert.ToUInt32%2A?displayProperty=fullName> 方法在内部使用 <xref:System.Int32.Parse%2A>。  如果字符串的格式无效，则 `Parse` 会引发异常，而 `TryParse` 会返回 [false](../../../csharp/language-reference/keywords/false.md)。  
  
## 示例  
 `Parse` 和 `TryParse` 方法会忽略字符串开头和末尾的空格，但所有其他字符必须是组成合适数值类型（int、long、ulong、float、decimal 等）的字符。  组成数字的字符中的任何空格都会导致错误。  例如，可以使用 `decimal.TryParse` 分析“10”、“10.3”、“  10  ”，但不能使用此方法分析从“10X”、“1 0”（注意空格）、“10 .3”（注意空格）、“10e1”（`float.TryParse` 在此处适用）等中分析出 10。  
  
 下面的示例演示了对 `Parse` 和 `TryParse` 的成功调用和不成功的调用。  
  
 [!code-cs[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/how-to-convert-a-string-_1_1.cs)]  
[!code-cs[csProgGuideTypes#25](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/how-to-convert-a-string-_1_2.cs)]  
[!code-cs[csProgGuideTypes#26](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/how-to-convert-a-string-_1_3.cs)]  
[!code-cs[csProgGuideTypes#27](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/how-to-convert-a-string-_1_4.cs)]  
[!code-cs[csProgGuideTypes#28](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/how-to-convert-a-string-_1_5.cs)]  
[!code-cs[csProgGuideTypes#100](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/how-to-convert-a-string-_1_6.cs)]  
  
## 示例  
 下表列出了 <xref:System.Convert> 类中可使用的一些方法。  
  
|数值类型|方法|  
|----------|--------|  
|`decimal`|<xref:System.Convert.ToDecimal%28System.String%29>|  
|`float`|<xref:System.Convert.ToSingle%28System.String%29>|  
|`double`|<xref:System.Convert.ToDouble%28System.String%29>|  
|`short`|<xref:System.Convert.ToInt16%28System.String%29>|  
|`int`|<xref:System.Convert.ToInt32%28System.String%29>|  
|`long`|<xref:System.Convert.ToInt64%28System.String%29>|  
|`ushort`|<xref:System.Convert.ToUInt16%28System.String%29>|  
|`uint`|<xref:System.Convert.ToUInt32%28System.String%29>|  
|`ulong`|<xref:System.Convert.ToUInt64%28System.String%29>|  
  
 此示例调用 <xref:System.Convert.ToInt32%28System.String%29?displayProperty=fullName> 方法将输入的 [string](../../../csharp/language-reference/keywords/string.md) 转换为 [int](../../../csharp/language-reference/keywords/int.md)。  代码将捕获此方法可能引发的最常见的两个异常：<xref:System.FormatException> 和 <xref:System.OverflowException>。  如果该数字可以递增而不溢出整数存储位置，则程序使结果加上 1 并打印输出。  
  
 [!code-cs[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/how-to-convert-a-string-_1_1.cs)]  
[!code-cs[csProgGuideTypes#24](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/how-to-convert-a-string-_1_7.cs)]  
  
## 请参阅  
 [类型](../../../csharp/programming-guide/types/index.md)   
 [如何：确定字符串是否表示数值](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)   
 [.NET Framework 4 格式设置实用工具](http://code.msdn.microsoft.com/NET-Framework-4-Formatting-9c4dae8d)