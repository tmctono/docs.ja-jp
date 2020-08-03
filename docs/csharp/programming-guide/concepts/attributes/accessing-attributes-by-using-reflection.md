---
title: リフレクションを使用した属性へのアクセス (C#)
description: GetCustomAttributes メソッドを使用して、C# でカスタム属性を使用して定義された情報を取得するには、リフレクションを使用します。
ms.date: 07/20/2015
ms.assetid: dce3a696-4ceb-489a-b5e4-322a83052f18
ms.openlocfilehash: 9425141d64fd061d0c1f628228693cce02f7bfa0
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925099"
---
# <a name="accessing-attributes-by-using-reflection-c"></a><span data-ttu-id="d3950-103">リフレクションを使用した属性へのアクセス (C#)</span><span class="sxs-lookup"><span data-stu-id="d3950-103">Accessing Attributes by Using Reflection (C#)</span></span>
<span data-ttu-id="d3950-104">カスタム属性を定義し、それらをソース コード内に配置することができても、その情報を取得して操作する手段がなければ、ほとんど価値はありません。</span><span class="sxs-lookup"><span data-stu-id="d3950-104">The fact that you can define custom attributes and place them in your source code would be of little value without some way of retrieving that information and acting on it.</span></span> <span data-ttu-id="d3950-105">リフレクションを使用すれば、カスタム属性を使用して定義された情報を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="d3950-105">By using reflection, you can retrieve the information that was defined with custom attributes.</span></span> <span data-ttu-id="d3950-106">鍵となるメソッドは `GetCustomAttributes` です。このメソッドは、ソース コード属性の実行時の等価オブジェクトを配列で返します。</span><span class="sxs-lookup"><span data-stu-id="d3950-106">The key method is `GetCustomAttributes`, which returns an array of objects that are the run-time equivalents of the source code attributes.</span></span> <span data-ttu-id="d3950-107">このメソッドには、いくつかのオーバー ロード バージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="d3950-107">This method has several overloaded versions.</span></span> <span data-ttu-id="d3950-108">詳細については、「<xref:System.Attribute>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3950-108">For more information, see <xref:System.Attribute>.</span></span>  
  
 <span data-ttu-id="d3950-109">次のような属性指定は、</span><span class="sxs-lookup"><span data-stu-id="d3950-109">An attribute specification such as:</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
```  
  
 <span data-ttu-id="d3950-110">概念的には次の記述と同じです。</span><span class="sxs-lookup"><span data-stu-id="d3950-110">is conceptually equivalent to this:</span></span>  
  
```csharp  
Author anonymousAuthorObject = new Author("P. Ackerman");  
anonymousAuthorObject.version = 1.1;  
```  
  
 <span data-ttu-id="d3950-111">ただし、属性について `SampleClass` が照会されるまで、コードは実行されません。</span><span class="sxs-lookup"><span data-stu-id="d3950-111">However, the code is not executed until `SampleClass` is queried for attributes.</span></span> <span data-ttu-id="d3950-112">`SampleClass` について `GetCustomAttributes` を呼び出すと、`Author` オブジェクトが作成され、上記のように初期化されます。</span><span class="sxs-lookup"><span data-stu-id="d3950-112">Calling `GetCustomAttributes` on `SampleClass` causes an `Author` object to be constructed and initialized as above.</span></span> <span data-ttu-id="d3950-113">クラスに他の属性がある場合は、他の属性オブジェクトも同様に作成されます。</span><span class="sxs-lookup"><span data-stu-id="d3950-113">If the class has other attributes, other attribute objects are constructed similarly.</span></span> <span data-ttu-id="d3950-114">`GetCustomAttributes` はその後、`Author` オブジェクトと配列内の他の属性オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="d3950-114">`GetCustomAttributes` then returns the `Author` object and any other attribute objects in an array.</span></span> <span data-ttu-id="d3950-115">その後、この配列を反復処理し、各配列要素の型に基づいてどの属性が適用されたかを確認して、属性オブジェクトから情報を抽出することができます。</span><span class="sxs-lookup"><span data-stu-id="d3950-115">You can then iterate over this array, determine what attributes were applied based on the type of each array element, and extract information from the attribute objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3950-116">例</span><span class="sxs-lookup"><span data-stu-id="d3950-116">Example</span></span>  
 <span data-ttu-id="d3950-117">完全な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d3950-117">Here is a complete example.</span></span> <span data-ttu-id="d3950-118">カスタム属性が定義され、複数のエンティティに適用された後、リフレクションを使用して取得されています。</span><span class="sxs-lookup"><span data-stu-id="d3950-118">A custom attribute is defined, applied to several entities, and retrieved via reflection.</span></span>  
  
```csharp  
// Multiuse attribute.  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // Multiuse attribute.  
]  
public class Author : System.Attribute  
{  
    string name;  
    public double version;  
  
    public Author(string name)  
    {  
        this.name = name;  
  
        // Default value.  
        version = 1.0;  
    }  
  
    public string GetName()  
    {  
        return name;  
    }  
}  
  
// Class with the Author attribute.  
[Author("P. Ackerman")]  
public class FirstClass  
{  
    // ...  
}  
  
// Class without the Author attribute.  
public class SecondClass  
{  
    // ...  
}  
  
// Class with multiple Author attributes.  
[Author("P. Ackerman"), Author("R. Koch", version = 2.0)]  
public class ThirdClass  
{  
    // ...  
}  
  
class TestAuthorAttribute  
{  
    static void Test()  
    {  
        PrintAuthorInfo(typeof(FirstClass));  
        PrintAuthorInfo(typeof(SecondClass));  
        PrintAuthorInfo(typeof(ThirdClass));  
    }  
  
    private static void PrintAuthorInfo(System.Type t)  
    {  
        System.Console.WriteLine("Author information for {0}", t);  
  
        // Using reflection.  
        System.Attribute[] attrs = System.Attribute.GetCustomAttributes(t);  // Reflection.  
  
        // Displaying output.  
        foreach (System.Attribute attr in attrs)  
        {  
            if (attr is Author)  
            {  
                Author a = (Author)attr;  
                System.Console.WriteLine("   {0}, version {1:f}", a.GetName(), a.version);  
            }  
        }  
    }  
}  
/* Output:  
    Author information for FirstClass  
       P. Ackerman, version 1.00  
    Author information for SecondClass  
    Author information for ThirdClass  
       R. Koch, version 2.00  
       P. Ackerman, version 1.00  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3950-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3950-119">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="d3950-120">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="d3950-120">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="d3950-121">属性に格納されている情報の取得</span><span class="sxs-lookup"><span data-stu-id="d3950-121">Retrieving Information Stored in Attributes</span></span>](../../../../standard/attributes/retrieving-information-stored-in-attributes.md)
- [<span data-ttu-id="d3950-122">リフレクション (C#)</span><span class="sxs-lookup"><span data-stu-id="d3950-122">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="d3950-123">属性 (C#)</span><span class="sxs-lookup"><span data-stu-id="d3950-123">Attributes (C#)</span></span>](./index.md)
- [<span data-ttu-id="d3950-124">カスタム属性の作成 (C#)</span><span class="sxs-lookup"><span data-stu-id="d3950-124">Creating Custom Attributes (C#)</span></span>](./creating-custom-attributes.md)
