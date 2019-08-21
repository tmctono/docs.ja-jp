---
title: ':: 演算子 - C# リファレンス'
ms.custom: seodec18
ms.date: 08/09/2019
f1_keywords:
- ::_CSharpKeyword
- global_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- namespace alias qualifier [C#]
- namespace [C#]
- global keyword [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 2aceb51747708b12fb3059b097b72206c78a9d5d
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971237"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="e7ff2-102">:: 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="e7ff2-102">:: operator (C# reference)</span></span>

<span data-ttu-id="e7ff2-103">エイリアスが設定された名前空間のメンバーにアクセスするには、名前空間エイリアス修飾子 `::` を使います。</span><span class="sxs-lookup"><span data-stu-id="e7ff2-103">Use the namespace alias qualifier `::` to access members of an aliased namespace.</span></span> <span data-ttu-id="e7ff2-104">`::` 修飾子は 2 つの識別子の間で使用します。</span><span class="sxs-lookup"><span data-stu-id="e7ff2-104">You use the `::` qualifier between two identifiers.</span></span> <span data-ttu-id="e7ff2-105">左側の識別子には、次のエイリアスのいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e7ff2-105">The left-hand identifier can be any of the following aliases:</span></span>

- <span data-ttu-id="e7ff2-106">[using エイリアス ディレクティブ](../keywords/using-directive.md)を使って作成された名前空間エイリアス:</span><span class="sxs-lookup"><span data-stu-id="e7ff2-106">A namespace alias created with the [using alias directive](../keywords/using-directive.md):</span></span>
  
  ```csharp
  using forwinforms = System.Drawing;
  using forwpf = System.Windows;
  
  public class Converters
  {
      public static forwpf::Point Convert(forwinforms::Point point) => new forwpf::Point(point.X, point.Y);
  }
  ```

- <span data-ttu-id="e7ff2-107">[extern エイリアス](../keywords/extern-alias.md)。</span><span class="sxs-lookup"><span data-stu-id="e7ff2-107">An [extern alias](../keywords/extern-alias.md).</span></span>
- <span data-ttu-id="e7ff2-108">`global` エイリアス。これはグローバル名前空間エイリアスです。</span><span class="sxs-lookup"><span data-stu-id="e7ff2-108">The `global` alias, which is the global namespace alias.</span></span> <span data-ttu-id="e7ff2-109">グローバル名前空間は、名前付き名前空間内で宣言されていない名前空間と型を含んだ名前空間です。</span><span class="sxs-lookup"><span data-stu-id="e7ff2-109">The global namespace is the namespace that contains namespaces and types that are not declared inside a named namespace.</span></span> <span data-ttu-id="e7ff2-110">`global` エイリアスを `::` 修飾子と共に使った場合は、ユーザー定義の名前空間エイリアス `global` が存在していたとしても、常にグローバル名前空間が参照されます。</span><span class="sxs-lookup"><span data-stu-id="e7ff2-110">When used with the `::` qualifier, the `global` alias always references the global namespace, even if there is the user-defined `global` namespace alias.</span></span>
  
  <span data-ttu-id="e7ff2-111">次の例では、`global` エイリアスを使って、グローバル名前空間のメンバーである .NET の <xref:System> 名前空間にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e7ff2-111">The following example uses the `global` alias to access the .NET <xref:System> namespace, which is a member of the global namespace.</span></span> <span data-ttu-id="e7ff2-112">`global` エイリアスを使わない場合は、`MyCompany.MyProduct` 名前空間のメンバーであるユーザー定義の `System` 名前空間がアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="e7ff2-112">Without the `global` alias, the user-defined `System` namespace, which is a member of the `MyCompany.MyProduct` namespace, would be accessed:</span></span>

  ```csharp
  namespace MyCompany.MyProduct.System
  {
      class Program
      {
          static void Main() => global::System.Console.WriteLine("Using global alias");
      }
  
      class Console
      {
          string Suggestion => "Consider renaming this class";
      }
  }
  ```
  
  > [!NOTE]
  > <span data-ttu-id="e7ff2-113">`global` キーワードは、`::` 修飾子の左側の識別子に指定した場合にのみ、グローバル名前空間エイリアスとなります。</span><span class="sxs-lookup"><span data-stu-id="e7ff2-113">The `global` keyword is the global namespace alias only when it's the left-hand identifier of the `::` qualifier.</span></span>

<span data-ttu-id="e7ff2-114">また、[メンバー アクセス演算子 `.`](member-access-operators.md#member-access-operator-) を使って、エイリアスが設定された名前空間のメンバーにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e7ff2-114">You can also use the [member access `.` operator](member-access-operators.md#member-access-operator-) to access members of an aliased namespace.</span></span> <span data-ttu-id="e7ff2-115">ただし、`.` 演算子は型のメンバーにアクセスするためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7ff2-115">However, the `.` operator is also used to access members of a type.</span></span> <span data-ttu-id="e7ff2-116">`::` 修飾子を使う場合、その左側の識別子は、同じ名前を持つ型または名前空間が存在したとしても、常に名前空間エイリアスを参照することが保証されます。</span><span class="sxs-lookup"><span data-stu-id="e7ff2-116">The `::` qualifier ensures that its left-hand identifier always references a namespace alias, even if there exists a type or namespace with the same name.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e7ff2-117">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="e7ff2-117">C# language specification</span></span>

<span data-ttu-id="e7ff2-118">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)に関するページの「[名前空間エイリアス修飾子](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e7ff2-118">For more information, see the [Namespace alias qualifiers](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e7ff2-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7ff2-119">See also</span></span>

- [<span data-ttu-id="e7ff2-120">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="e7ff2-120">C# reference</span></span>](../index.md)
- [<span data-ttu-id="e7ff2-121">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="e7ff2-121">C# operators</span></span>](index.md)
- [<span data-ttu-id="e7ff2-122">名前空間の使用</span><span class="sxs-lookup"><span data-stu-id="e7ff2-122">Using namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)
