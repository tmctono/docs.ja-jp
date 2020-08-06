---
title: C++ テンプレートと C# ジェネリックの違い - C# プログラミング ガイド
description: C++ テンプレートと C# ジェネリックの違いについて説明します。 どちらもパラメーター化された型のサポートを提供する言語機能です。
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], vs. C++ templates
ms.assetid: 1da6beeb-d4a4-4da0-87b7-0cfbe04920b7
ms.openlocfilehash: f405e2d4bef730317703b3b8470edef5b89f0bed
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301932"
---
# <a name="differences-between-c-templates-and-c-generics-c-programming-guide"></a><span data-ttu-id="31f96-104">C++ テンプレートと C# ジェネリックの違い (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="31f96-104">Differences Between C++ Templates and C# Generics (C# Programming Guide)</span></span>
<span data-ttu-id="31f96-105">C# ジェネリックと C++ テンプレートのいずれも、パラメーター化された型のサポートを提供する言語機能です。</span><span class="sxs-lookup"><span data-stu-id="31f96-105">C# Generics and C++ templates are both language features that provide support for parameterized types.</span></span> <span data-ttu-id="31f96-106">ただし、これら 2 つにはさまざまな違いがあります。</span><span class="sxs-lookup"><span data-stu-id="31f96-106">However, there are many differences between the two.</span></span> <span data-ttu-id="31f96-107">構文レベルでは、C# ジェネリックの場合、パラメーター化された型の取り扱いが単純であり、C++ テンプレートのような複雑さがありません。</span><span class="sxs-lookup"><span data-stu-id="31f96-107">At the syntax level, C# generics are a simpler approach to parameterized types without the complexity of C++ templates.</span></span> <span data-ttu-id="31f96-108">さらに、C++ テンプレートで提供されるすべての機能が、C# でも提供されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="31f96-108">In addition, C# does not attempt to provide all of the functionality that C++ templates provide.</span></span> <span data-ttu-id="31f96-109">実装レベルでは、C# ジェネリック型の代入は実行時に行われ、その結果、インスタンス化されたオブジェクトのジェネリック型情報が保存されるという点が最も大きな違いです。</span><span class="sxs-lookup"><span data-stu-id="31f96-109">At the implementation level, the primary difference is that C# generic type substitutions are performed at runtime and generic type information is thereby preserved for instantiated objects.</span></span> <span data-ttu-id="31f96-110">詳細については、「[ランタイムのジェネリック](./generics-in-the-run-time.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31f96-110">For more information, see [Generics in the Run Time](./generics-in-the-run-time.md).</span></span>  
  
 <span data-ttu-id="31f96-111">C# ジェネリックと C++ テンプレートの主な違いを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="31f96-111">The following are the key differences between C# Generics and C++ templates:</span></span>  
  
- <span data-ttu-id="31f96-112">C# ジェネリックは、C++ テンプレートほど柔軟ではありません。</span><span class="sxs-lookup"><span data-stu-id="31f96-112">C# generics do not provide the same amount of flexibility as C++ templates.</span></span> <span data-ttu-id="31f96-113">たとえば、C# ジェネリック クラスでは、ユーザー定義演算子は呼び出すことができますが、算術演算子を呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="31f96-113">For example, it is not possible to call arithmetic operators in a C# generic class, although it is possible to call user defined operators.</span></span>  
  
- <span data-ttu-id="31f96-114">C# では、`template C<int i> {}` などの非型テンプレート パラメーターを使用できません。</span><span class="sxs-lookup"><span data-stu-id="31f96-114">C# does not allow non-type template parameters, such as `template C<int i> {}`.</span></span>  
  
- <span data-ttu-id="31f96-115">C# は、明示的な特殊化 (特定の型のテンプレートのカスタム実装) をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="31f96-115">C# does not support explicit specialization; that is, a custom implementation of a template for a specific type.</span></span>  
  
- <span data-ttu-id="31f96-116">C# は、部分的な特殊化 (型引数のサブセットのカスタム実装) をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="31f96-116">C# does not support partial specialization: a custom implementation for a subset of the type arguments.</span></span>  
  
- <span data-ttu-id="31f96-117">C# では、型パラメーターをジェネリック型の基底クラスとして使用できません。</span><span class="sxs-lookup"><span data-stu-id="31f96-117">C# does not allow the type parameter to be used as the base class for the generic type.</span></span>  
  
- <span data-ttu-id="31f96-118">C# では、型パラメーターに既定の型を割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="31f96-118">C# does not allow type parameters to have default types.</span></span>  
  
- <span data-ttu-id="31f96-119">C# では、構築された型はジェネリックとして使用できますが、ジェネリック型パラメーター自体はジェネリックにできません。</span><span class="sxs-lookup"><span data-stu-id="31f96-119">In C#, a generic type parameter cannot itself be a generic, although constructed types can be used as generics.</span></span> <span data-ttu-id="31f96-120">C++ では、テンプレート パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="31f96-120">C++ does allow template parameters.</span></span>  
  
- <span data-ttu-id="31f96-121">C++ では、テンプレート内のすべての型パラメーターに対して有効でない可能性のあるコードを使用できます。このようなコードは、型パラメーターとして使用されている特定の型に対してチェックされます。</span><span class="sxs-lookup"><span data-stu-id="31f96-121">C++ allows code that might not be valid for all type parameters in the template, which is then checked for the specific type used as the type parameter.</span></span> <span data-ttu-id="31f96-122">C# では、制約を満たすすべての型で正常に動作するようにクラスのコードを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31f96-122">C# requires code in a class to be written in such a way that it will work with any type that satisfies the constraints.</span></span> <span data-ttu-id="31f96-123">たとえば、C++ では、型パラメーターのオブジェクトで算術演算子 `+` および `-` を使用し、これらの演算子をサポートしない型を使ってテンプレートをインスタンス化するとエラーを生成する関数を記述できます。</span><span class="sxs-lookup"><span data-stu-id="31f96-123">For example, in C++ it is possible to write a function that uses the arithmetic operators `+` and `-` on objects of the type parameter, which will produce an error at the time of instantiation of the template with a type that does not support these operators.</span></span> <span data-ttu-id="31f96-124">C# では、このような関数は許可されません。許可される言語構成要素は、制約から推定できるものだけに限られます。</span><span class="sxs-lookup"><span data-stu-id="31f96-124">C# disallows this; the only language constructs allowed are those that can be deduced from the constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31f96-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="31f96-125">See also</span></span>

- [<span data-ttu-id="31f96-126">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="31f96-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="31f96-127">ジェネリックの概要</span><span class="sxs-lookup"><span data-stu-id="31f96-127">Introduction to Generics</span></span>](./index.md)
- [<span data-ttu-id="31f96-128">テンプレート</span><span class="sxs-lookup"><span data-stu-id="31f96-128">Templates</span></span>](/cpp/cpp/templates-cpp)
