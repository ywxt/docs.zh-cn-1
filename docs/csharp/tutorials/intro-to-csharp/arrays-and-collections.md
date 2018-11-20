---
title: 使用集合 - C# 教程简介
description: 在本教程中通过探索列表集合了解 C#。
ms.date: 10/13/2017
ms.custom: mvc
ms.openlocfilehash: eaf921be2bd50b6e346f57f42e17f151ff336821
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2018
ms.locfileid: "50205277"
---
# <a name="learn-to-manage-data-collections-using-the-generic-list-type"></a><span data-ttu-id="f3906-103">了解如何使用泛型列表类型管理数据集合</span><span class="sxs-lookup"><span data-stu-id="f3906-103">Learn to manage data collections using the generic list type</span></span>

<span data-ttu-id="f3906-104">本介绍性教程介绍了 C# 语言和 <xref:System.Collections.Generic.List%601> 类的基础知识。</span><span class="sxs-lookup"><span data-stu-id="f3906-104">This introductory tutorial provides an introduction to the C# language and the basics of the <xref:System.Collections.Generic.List%601> class.</span></span>

<span data-ttu-id="f3906-105">本教程要求你有一台可用于开发的计算机。</span><span class="sxs-lookup"><span data-stu-id="f3906-105">This tutorial expects you to have a machine you can use for development.</span></span> <span data-ttu-id="f3906-106">.NET 主题 [10 分钟入门](https://www.microsoft.com/net/core)介绍了如何在 Mac、PC 或 Linux 上设置本地开发环境。</span><span class="sxs-lookup"><span data-stu-id="f3906-106">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="f3906-107">[熟悉开发工具](local-environment.md)不仅简要概述了将用到的命令，还收录了详细信息链接。</span><span class="sxs-lookup"><span data-stu-id="f3906-107">A quick overview of the commands you'll use is in [Become familiar with the development tools](local-environment.md), with links to more details.</span></span>

## <a name="a-basic-list-example"></a><span data-ttu-id="f3906-108">基本列表示例</span><span class="sxs-lookup"><span data-stu-id="f3906-108">A basic list example</span></span>

<span data-ttu-id="f3906-109">创建名为 list-tutorial 的目录。</span><span class="sxs-lookup"><span data-stu-id="f3906-109">Create a directory named **list-tutorial**.</span></span> <span data-ttu-id="f3906-110">将新建的目录设为当前目录，并运行 `dotnet new console`。</span><span class="sxs-lookup"><span data-stu-id="f3906-110">Make that the current directory and run `dotnet new console`.</span></span>

> [!NOTE]
> <span data-ttu-id="f3906-111">如果你刚完成 [10 分钟 .NET 入门](https://www.microsoft.com/net)，则可以继续使用刚刚创建的 myApp 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f3906-111">If you just completed [Get started with .NET in 10 minutes](https://www.microsoft.com/net), you can keep using the myApp application that you just created.</span></span>

<span data-ttu-id="f3906-112">在常用编辑器中，打开 Program.cs，并将现有代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="f3906-112">Open **Program.cs** in your favorite editor, and replace the existing code with the following:</span></span>

```csharp
using System;
using System.Collections.Generic;

namespace list_tutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

<span data-ttu-id="f3906-113">将 `<name>` 替换为自己的名称。</span><span class="sxs-lookup"><span data-stu-id="f3906-113">Replace `<name>` with your name.</span></span> <span data-ttu-id="f3906-114">保存 Program.cs。</span><span class="sxs-lookup"><span data-stu-id="f3906-114">Save **Program.cs**.</span></span> <span data-ttu-id="f3906-115">在控制台窗口中键入 `dotnet run`，试运行看看。</span><span class="sxs-lookup"><span data-stu-id="f3906-115">Type `dotnet run` in your console window to try it.</span></span>

<span data-ttu-id="f3906-116">刚刚创建了一个字符串列表，并向其中添加了三个名称，再输出了全部大写的名称。</span><span class="sxs-lookup"><span data-stu-id="f3906-116">You've just created a list of strings, added three names to that list, and printed out the names in all CAPS.</span></span> <span data-ttu-id="f3906-117">循环读取整个列表需要用到在前面的教程中学到的概念。</span><span class="sxs-lookup"><span data-stu-id="f3906-117">You're using concepts that you've learned in earlier tutorials to loop through the list.</span></span>

<span data-ttu-id="f3906-118">用于显示名称的代码使用[字符串内插](../../language-reference/tokens/interpolated.md)功能。</span><span class="sxs-lookup"><span data-stu-id="f3906-118">The code to display names makes use of the [string interpolation](../../language-reference/tokens/interpolated.md) feature.</span></span>  <span data-ttu-id="f3906-119">如果 `string` 前面有 `$`符号，可以在字符串声明中嵌入 C# 代码。</span><span class="sxs-lookup"><span data-stu-id="f3906-119">When you precede a `string` with the `$` character, you can embed C# code in the string declaration.</span></span> <span data-ttu-id="f3906-120">实际字符串使用自己生成的值替换该 C# 代码。</span><span class="sxs-lookup"><span data-stu-id="f3906-120">The actual string replaces that C# code with the value it generates.</span></span> <span data-ttu-id="f3906-121">在此示例中，`{name.ToUpper()}` 被替换为各个转换为大写字母的名称，因为调用了 <xref:System.String.ToUpper%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="f3906-121">In this example, it replaces the `{name.ToUpper()}` with each name, converted to capital letters, because you called the <xref:System.String.ToUpper%2A> method.</span></span>

<span data-ttu-id="f3906-122">接下来将进一步探索。</span><span class="sxs-lookup"><span data-stu-id="f3906-122">Let's keep exploring.</span></span>

## <a name="modify-list-contents"></a><span data-ttu-id="f3906-123">修改列表内容</span><span class="sxs-lookup"><span data-stu-id="f3906-123">Modify list contents</span></span>

<span data-ttu-id="f3906-124">创建的集合使用 <xref:System.Collections.Generic.List%601> 类型。</span><span class="sxs-lookup"><span data-stu-id="f3906-124">The collection you created uses the <xref:System.Collections.Generic.List%601> type.</span></span> <span data-ttu-id="f3906-125">此类型存储一系列元素。</span><span class="sxs-lookup"><span data-stu-id="f3906-125">This type stores sequences of elements.</span></span> <span data-ttu-id="f3906-126">元素类型是在尖括号内指定。</span><span class="sxs-lookup"><span data-stu-id="f3906-126">You specify the type of the elements between the angle brackets.</span></span>

<span data-ttu-id="f3906-127"><xref:System.Collections.Generic.List%601> 类型的一个重要方面是，既可以扩大，也可以收缩，方便用户添加或删除元素。</span><span class="sxs-lookup"><span data-stu-id="f3906-127">One important aspect of this <xref:System.Collections.Generic.List%601> type is that it can grow or shrink, enabling you to add or remove elements.</span></span> <span data-ttu-id="f3906-128">在 `Main` 方法的右 `}` 前添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="f3906-128">Add this code before the closing `}` in the `Main` method:</span></span>

```csharp
Console.WriteLine();
names.Add("Maria");
names.Add("Bill");
names.Remove("Ana");
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="f3906-129">又向列表的末尾添加了两个名称。</span><span class="sxs-lookup"><span data-stu-id="f3906-129">You've added two more names to the end of the list.</span></span> <span data-ttu-id="f3906-130">同时，也删除了一个名称。</span><span class="sxs-lookup"><span data-stu-id="f3906-130">You've also removed one as well.</span></span> <span data-ttu-id="f3906-131">保存此文件，并键入 `dotnet run`，试运行看看。</span><span class="sxs-lookup"><span data-stu-id="f3906-131">Save the file, and type `dotnet run` to try it.</span></span>

<span data-ttu-id="f3906-132">借助 <xref:System.Collections.Generic.List%601>，还可以按索引引用各项。</span><span class="sxs-lookup"><span data-stu-id="f3906-132">The <xref:System.Collections.Generic.List%601> enables you to reference individual items by **index** as well.</span></span> <span data-ttu-id="f3906-133">索引位于列表名称后面的 `[` 和 `]` 令牌之间。</span><span class="sxs-lookup"><span data-stu-id="f3906-133">You place the index between `[` and `]` tokens following the list name.</span></span> <span data-ttu-id="f3906-134">C# 对第一个索引使用 0。</span><span class="sxs-lookup"><span data-stu-id="f3906-134">C# uses 0 for the first index.</span></span> <span data-ttu-id="f3906-135">将以下代码添加到刚才添加的代码的正下方，并试运行看看：</span><span class="sxs-lookup"><span data-stu-id="f3906-135">Add this code directly below the code you just added and try it:</span></span>

```csharp
Console.WriteLine($"My name is {names[0]}");
Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");
```

<span data-ttu-id="f3906-136">不得访问超出列表末尾的索引。</span><span class="sxs-lookup"><span data-stu-id="f3906-136">You cannot access an index beyond the end of the list.</span></span> <span data-ttu-id="f3906-137">请注意，索引是从 0 开始编制，因此最大有效索引是用列表项数减 1 计算得出。</span><span class="sxs-lookup"><span data-stu-id="f3906-137">Remember that indices start at 0, so the largest valid index is one less than the number of items in the list.</span></span> <span data-ttu-id="f3906-138">可以使用 <xref:System.Collections.Generic.List%601.Count%2A> 属性确定列表长度。</span><span class="sxs-lookup"><span data-stu-id="f3906-138">You can check how long the list is using the <xref:System.Collections.Generic.List%601.Count%2A> property.</span></span> <span data-ttu-id="f3906-139">在 Main 方法的末尾，添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="f3906-139">Add the following code at the end of the Main method:</span></span>

```csharp
Console.WriteLine($"The list has {names.Count} people in it");
 ```

<span data-ttu-id="f3906-140">保存此文件，并再次键入 `dotnet run` 看看结果如何。</span><span class="sxs-lookup"><span data-stu-id="f3906-140">Save the file, and type `dotnet run` again to see the results.</span></span>

## <a name="search-and-sort-lists"></a><span data-ttu-id="f3906-141">搜索列表并进行排序</span><span class="sxs-lookup"><span data-stu-id="f3906-141">Search and sort lists</span></span>

<span data-ttu-id="f3906-142">我们的示例使用的列表较小，但大家的应用程序创建的列表通常可能会包含更多元素，有时可能会包含数以千计的元素。</span><span class="sxs-lookup"><span data-stu-id="f3906-142">Our samples use relatively small lists, but your applications may often create lists with many more elements, sometimes numbering in the thousands.</span></span> <span data-ttu-id="f3906-143">若要在更大的集合中查找元素，需要在列表中搜索不同的项。</span><span class="sxs-lookup"><span data-stu-id="f3906-143">To find elements in these larger collections, you need to search the list for different items.</span></span> <span data-ttu-id="f3906-144"><xref:System.Collections.Generic.List%601.IndexOf%2A> 方法可搜索项，并返回此项的索引。</span><span class="sxs-lookup"><span data-stu-id="f3906-144">The <xref:System.Collections.Generic.List%601.IndexOf%2A> method searches for an item and returns the index of the item.</span></span> <span data-ttu-id="f3906-145">将以下代码添加到 `Main` 方法的底部：</span><span class="sxs-lookup"><span data-stu-id="f3906-145">Add this code to the bottom of your `Main` method:</span></span>

```csharp
var index = names.IndexOf("Felipe");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
} else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
}

index = names.IndexOf("Not Found");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
} else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");

}
```

<span data-ttu-id="f3906-146">还可以对列表中的项进行排序。</span><span class="sxs-lookup"><span data-stu-id="f3906-146">The items in your list can be sorted as well.</span></span> <span data-ttu-id="f3906-147"><xref:System.Collections.Generic.List%601.Sort%2A> 方法按正常顺序（按字母顺序，如果是字符串的话）对列表中的所有项进行排序。</span><span class="sxs-lookup"><span data-stu-id="f3906-147">The <xref:System.Collections.Generic.List%601.Sort%2A> method sorts all the items in the list in their normal order (alphabetically in the case of strings).</span></span> <span data-ttu-id="f3906-148">将以下代码添加到 `Main` 方法的底部：</span><span class="sxs-lookup"><span data-stu-id="f3906-148">Add this code to the bottom of our `Main` method:</span></span>

```csharp
names.Sort();
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="f3906-149">保存此文件，并键入 `dotnet run`，试运行此最新版程序。</span><span class="sxs-lookup"><span data-stu-id="f3906-149">Save the file and type `dotnet run` to try this latest version.</span></span>

<span data-ttu-id="f3906-150">开始进入下一部分前，先将当前代码移到单独的方法中。</span><span class="sxs-lookup"><span data-stu-id="f3906-150">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="f3906-151">这样一来，可以更轻松地开始处理新示例。</span><span class="sxs-lookup"><span data-stu-id="f3906-151">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="f3906-152">将 `Main` 方法重命名为 `WorkingWithStrings`，并编写调用 `WorkingWithStrings` 的新 `Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="f3906-152">Rename your `Main` method to `WorkingWithStrings` and write a new `Main` method that calls `WorkingWithStrings`.</span></span> <span data-ttu-id="f3906-153">完成后，代码应如下所示：</span><span class="sxs-lookup"><span data-stu-id="f3906-153">When you have finished, your code should look like this:</span></span>

```csharp
using System;
using System.Collections.Generic;

namespace list_tutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            WorkingWithStrings();
        }

        public static void WorkingWithStrings()
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine();
            names.Add("Maria");
            names.Add("Bill");
            names.Remove("Ana");
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine($"My name is {names[0]}");
            Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");

            Console.WriteLine($"The list has {names.Count} people in it");

            var index = names.IndexOf("Felipe");
            Console.WriteLine($"The name {names[index]} is at index {index}");

            var notFound = names.IndexOf("Not Found");
            Console.WriteLine($"When an item is not found, IndexOf returns {notFound}");

            names.Sort();
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

## <a name="lists-of-other-types"></a><span data-ttu-id="f3906-154">其他类型的列表</span><span class="sxs-lookup"><span data-stu-id="f3906-154">Lists of other types</span></span>

<span data-ttu-id="f3906-155">到目前为止，大家一直在列表中使用 `string` 类型。</span><span class="sxs-lookup"><span data-stu-id="f3906-155">You've been using the `string` type in lists so far.</span></span> <span data-ttu-id="f3906-156">接下来，将让 <xref:System.Collections.Generic.List%601> 使用其他类型。</span><span class="sxs-lookup"><span data-stu-id="f3906-156">Let's make a <xref:System.Collections.Generic.List%601> using a different type.</span></span> <span data-ttu-id="f3906-157">那就生成一组数字吧。</span><span class="sxs-lookup"><span data-stu-id="f3906-157">Let's build a set of numbers.</span></span>

<span data-ttu-id="f3906-158">将以下代码添加到新 `Main` 方法的底部：</span><span class="sxs-lookup"><span data-stu-id="f3906-158">Add the following to the bottom of your new `Main` method:</span></span>

```csharp
var fibonacciNumbers = new List<int> {1, 1};
```

<span data-ttu-id="f3906-159">这会创建一个整数列表，并将头两个整数设置为值 1。</span><span class="sxs-lookup"><span data-stu-id="f3906-159">That creates a list of integers, and sets the first two integers to the value 1.</span></span> <span data-ttu-id="f3906-160">这些是斐波那契数列（一系列数字）的头两个值。</span><span class="sxs-lookup"><span data-stu-id="f3906-160">These are the first two values of a *Fibonacci Sequence*, a sequence of numbers.</span></span> <span data-ttu-id="f3906-161">斐波那契数列中的每个数字都是前两个数字之和。</span><span class="sxs-lookup"><span data-stu-id="f3906-161">Each next Fibonacci number is found by taking the sum of the previous two numbers.</span></span> <span data-ttu-id="f3906-162">添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="f3906-162">Add this code:</span></span>

```csharp
var previous = fibonacciNumbers[fibonacciNumbers.Count - 1];
var previous2 = fibonacciNumbers[fibonacciNumbers.Count - 2];

fibonacciNumbers.Add(previous + previous2);

foreach(var item in fibonacciNumbers)
    Console.WriteLine(item);
```

<span data-ttu-id="f3906-163">保存此文件，并键入 `dotnet run` 看看结果如何。</span><span class="sxs-lookup"><span data-stu-id="f3906-163">Save the file and type `dotnet run` to see the results.</span></span>

> [!TIP]
> <span data-ttu-id="f3906-164">为了能够集中精力探究此部分，可以注释掉调用 `WorkingWithStrings();` 的代码。</span><span class="sxs-lookup"><span data-stu-id="f3906-164">To concentrate on just this section, you can comment out the code that calls `WorkingWithStrings();`.</span></span> <span data-ttu-id="f3906-165">只需在此调用前添加两个 `/` 字符即可，如 `// WorkingWithStrings();`。</span><span class="sxs-lookup"><span data-stu-id="f3906-165">Just put two `/` characters in front of the call like this:  `// WorkingWithStrings();`.</span></span>

## <a name="challenge"></a><span data-ttu-id="f3906-166">挑战</span><span class="sxs-lookup"><span data-stu-id="f3906-166">Challenge</span></span>

<span data-ttu-id="f3906-167">看看能不能将本课程中的一些概念与前面的课程融会贯通。</span><span class="sxs-lookup"><span data-stu-id="f3906-167">See if you can put together some of the concepts from this and earlier lessons.</span></span> <span data-ttu-id="f3906-168">使用斐波那契数列，扩展当前生成的程序。</span><span class="sxs-lookup"><span data-stu-id="f3906-168">Expand on what you've built so far with Fibonacci Numbers.</span></span> <span data-ttu-id="f3906-169">试着编写代码，生成此序列中的前 20 个数字。</span><span class="sxs-lookup"><span data-stu-id="f3906-169">Try to write the code to generate the first 20 numbers in the sequence.</span></span> <span data-ttu-id="f3906-170">（作为提示，第 20 个斐波纳契数是 6765。）</span><span class="sxs-lookup"><span data-stu-id="f3906-170">(As a hint, the 20th Fibonacci number is 6765.)</span></span>

## <a name="complete-challenge"></a><span data-ttu-id="f3906-171">完成挑战</span><span class="sxs-lookup"><span data-stu-id="f3906-171">Complete challenge</span></span>

<span data-ttu-id="f3906-172">可以[查看 GitHub 上的完成示例代码](https://github.com/dotnet/samples/tree/master/csharp/list-quickstart/Program.cs#L13-L23)，了解示例解决方案</span><span class="sxs-lookup"><span data-stu-id="f3906-172">You can see an example solution by [looking at the finished sample code on GitHub](https://github.com/dotnet/samples/tree/master/csharp/list-quickstart/Program.cs#L13-L23)</span></span>

<span data-ttu-id="f3906-173">在循环的每次迭代中，取此列表中的最后两个整数进行求和，并将计算出的总和值添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="f3906-173">With each iteration of the loop, you're taking the last two integers in the list, summing them, and adding that value to the list.</span></span> <span data-ttu-id="f3906-174">循环会一直重复运行到列表中有 20 个项为止。</span><span class="sxs-lookup"><span data-stu-id="f3906-174">The loop repeats until you've added 20 items to the list.</span></span>

<span data-ttu-id="f3906-175">恭喜！已完成“列表集合”教程。</span><span class="sxs-lookup"><span data-stu-id="f3906-175">Congratulations, you've completed the list tutorial.</span></span> <span data-ttu-id="f3906-176">可以在自己的开发环境中继续学习[类简介](introduction-to-classes.md)教程。</span><span class="sxs-lookup"><span data-stu-id="f3906-176">You can continue with the [Introduction to classes](introduction-to-classes.md) tutorial in your own development environment.</span></span>

<span data-ttu-id="f3906-177">若要详细了解如何使用 `List` 类型，可以参阅有关[集合](../../../standard/collections/index.md)的 [.NET 指南](../../../standard/index.md)主题。</span><span class="sxs-lookup"><span data-stu-id="f3906-177">You can learn more about working with the `List` type in the [.NET Guide](../../../standard/index.md) topic on [collections](../../../standard/collections/index.md).</span></span> <span data-ttu-id="f3906-178">还可以了解其他许多集合类型。</span><span class="sxs-lookup"><span data-stu-id="f3906-178">You'll also learn about many other collection types.</span></span>