---
title: 一维数组 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: 316f8f59b86294b1f344b31f7355017ebd992362
ms.sourcegitcommit: 8598d446303b545eed2d520a6ccd061c1a7d00cb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2018
ms.locfileid: "53334751"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a>一维数组（C# 编程指南）

可以声明五个整数的一维数组，如以下示例所示：  
  
 [!code-csharp[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]  
  
 此数组包含从 `array[0]` 到 `array[4]` 的元素。 [new](../../../csharp/language-reference/keywords/new.md) 运算符用于创建数组并将数组元素初始化为其默认值。 在此示例中，所有数组元素都将被初始化为零。  
  
 可使用相同方式声明存储字符串元素的数组。 例如:  
  
 [!code-csharp[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]  
  
## <a name="array-initialization"></a>数组初始化

 可以在声明时初始化数组，在这种情况下，无需长度说明符，因为它已由初始化列表中的元素数目提供。 例如:  
  
 [!code-csharp[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]  
  
 可使用相同方式初始化字符串数组。 下面是一个字符串数组的声明，其中每个数组元素都由一天的名称初始化：  
  
 [!code-csharp[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]  
  
 如果在声明时初始化数组，可以使用以下快捷方式：  
  
 [!code-csharp[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]  
  
 可以在不初始化的情况下声明数组变量，但必须使用 `new` 运算符向此变量分配数组。 例如:  
  
 [!code-csharp[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]  
  
 C# 3.0 引入了隐式类型化数组。 有关详细信息，请参阅[隐式类型化数组](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md)。  
  
## <a name="value-type-and-reference-type-arrays"></a>值类型和引用类型数组

 请考虑以下数组声明：  
  
 [!code-csharp[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]  
  
 此语句的结果取决于 `SomeType` 是值类型还是引用类型。 如果它是值类型，该语句将创建一个 10 个元素的数组，其中每个元素的类型都为 `SomeType`。 如果 `SomeType` 是引用类型，该语句将创建一个 10 个元素的数组，其中每个元素都将被初始化为空引用。  
  
 有关值类型和引用类型的详细信息，请参阅[类型](../../../csharp/language-reference/keywords/types.md)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Array>  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [数组](../../../csharp/programming-guide/arrays/index.md)  
- [多维数组](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
- [交错数组](../../../csharp/programming-guide/arrays/jagged-arrays.md)
