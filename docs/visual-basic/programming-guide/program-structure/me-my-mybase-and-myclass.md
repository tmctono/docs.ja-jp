---
title: Visual Basic における Me、My、MyBase、MyClass
ms.date: 07/20/2015
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
helpviewer_keywords:
- My object
- self-reference [Visual Basic], Me keyword
- MyClass keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], referring to the current instance of an object
- Me keyword [Visual Basic]
- self-reference
- current instance [Visual Basic], Me keyword
- MyBase keyword [Visual Basic], relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
ms.openlocfilehash: 3eca756429c5fec8f324a17350844b59baf9ccf7
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586260"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="81879-102">Visual Basic における Me、My、MyBase、MyClass</span><span class="sxs-lookup"><span data-stu-id="81879-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="81879-103">`Me`、 `My`、 `MyBase`、および`MyClass`Visual Basic で名前は似ていますが、さまざまな目的があります。</span><span class="sxs-lookup"><span data-stu-id="81879-103">`Me`, `My`, `MyBase`, and `MyClass` in Visual Basic have similar names, but different purposes.</span></span> <span data-ttu-id="81879-104">このトピックでは、それらを区別するために、これらのエンティティの各をについて説明します。</span><span class="sxs-lookup"><span data-stu-id="81879-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="81879-105">Me</span><span class="sxs-lookup"><span data-stu-id="81879-105">Me</span></span>  
 <span data-ttu-id="81879-106">`Me`キーワードはクラスまたは構造体の現在のコードが実行されているは、特定のインスタンスを参照する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="81879-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="81879-107">`Me` オブジェクト変数または構造体変数を参照する現在のインスタンスのいずれかのように動作します。</span><span class="sxs-lookup"><span data-stu-id="81879-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="81879-108">使用して`Me`はクラスまたは構造体の現在実行中のインスタンスに関する情報を別のクラス、構造体、またはモジュール内のプロシージャに渡すために特に便利です。</span><span class="sxs-lookup"><span data-stu-id="81879-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="81879-109">たとえば、モジュールに、次の手順があるとします。</span><span class="sxs-lookup"><span data-stu-id="81879-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="81879-110">このプロシージャを呼び出すしの現在のインスタンスを渡すことができます、<xref:System.Windows.Forms.Form>クラスを次のステートメントを使用して、引数として。</span><span class="sxs-lookup"><span data-stu-id="81879-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="81879-111">My</span><span class="sxs-lookup"><span data-stu-id="81879-111">My</span></span>  
 <span data-ttu-id="81879-112">`My`機能が多数のコンピューター、アプリケーション、設定、リソースとやり取りする Visual Basic のユーザーを有効にすると、.NET Framework クラスを簡単かつ直感的なアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="81879-112">The `My` feature provides easy and intuitive access to a number of .NET Framework classes, enabling the Visual Basic user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="81879-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="81879-113">MyBase</span></span>  
 <span data-ttu-id="81879-114">`MyBase`キーワードはクラスの現在のインスタンスの基本クラスを参照するオブジェクト変数のように動作します。</span><span class="sxs-lookup"><span data-stu-id="81879-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="81879-115">`MyBase` 通常オーバーライドまたは派生クラスでシャドウされている基本クラスのメンバーへのアクセスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="81879-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="81879-116">`MyBase.New` 派生クラスのコンス トラクターから基本クラスのコンス トラクターを明示的に呼び出すに使用されます。</span><span class="sxs-lookup"><span data-stu-id="81879-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="81879-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="81879-117">MyClass</span></span>  
 <span data-ttu-id="81879-118">`MyClass`キーワードが最初に実装されているクラスの現在のインスタンスを参照するオブジェクト変数のように動作します。</span><span class="sxs-lookup"><span data-stu-id="81879-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="81879-119">`MyClass` ような`Me`、上のすべてのメソッド呼び出しとして扱われます、メソッドしますが、`NotOverridable`します。</span><span class="sxs-lookup"><span data-stu-id="81879-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81879-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="81879-120">See also</span></span>

- [<span data-ttu-id="81879-121">継承の基本</span><span class="sxs-lookup"><span data-stu-id="81879-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
