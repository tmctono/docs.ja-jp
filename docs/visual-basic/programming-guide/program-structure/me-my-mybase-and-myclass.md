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
ms.openlocfilehash: 7df146e09a1d7cd730f4cf539d6823f7ced44bd1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002533"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="fa8d6-102">Visual Basic における Me、My、MyBase、MyClass</span><span class="sxs-lookup"><span data-stu-id="fa8d6-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="fa8d6-103">`Me`、`My`、`MyBase`、および `MyClass` Visual Basic の名前は似ていますが、目的は異なります。</span><span class="sxs-lookup"><span data-stu-id="fa8d6-103">`Me`, `My`, `MyBase`, and `MyClass` in Visual Basic have similar names, but different purposes.</span></span> <span data-ttu-id="fa8d6-104">このトピックでは、これらの各エンティティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fa8d6-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="fa8d6-105">Me</span><span class="sxs-lookup"><span data-stu-id="fa8d6-105">Me</span></span>  
 <span data-ttu-id="fa8d6-106">@No__t-0 キーワードは、コードが現在実行されているクラスまたは構造体の特定のインスタンスを参照する手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="fa8d6-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="fa8d6-107">`Me` は、オブジェクト変数または現在のインスタンスを参照する構造体変数のように動作します。</span><span class="sxs-lookup"><span data-stu-id="fa8d6-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="fa8d6-108">@No__t-0 を使用すると、クラスまたは構造体の現在実行中のインスタンスに関する情報を、別のクラス、構造体、またはモジュール内のプロシージャに渡す場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="fa8d6-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="fa8d6-109">たとえば、モジュールに次のプロシージャがあるとします。</span><span class="sxs-lookup"><span data-stu-id="fa8d6-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="fa8d6-110">次のステートメントを使用して、このプロシージャを呼び出して、<xref:System.Windows.Forms.Form> クラスの現在のインスタンスを引数として渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="fa8d6-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="fa8d6-111">My</span><span class="sxs-lookup"><span data-stu-id="fa8d6-111">My</span></span>  
 <span data-ttu-id="fa8d6-112">@No__t 0 の機能を使用すると、さまざまな .NET Framework クラスに簡単かつ直感的にアクセスできるので、Visual Basic ユーザーは、コンピューター、アプリケーション、設定、リソースなどと対話できます。</span><span class="sxs-lookup"><span data-stu-id="fa8d6-112">The `My` feature provides easy and intuitive access to a number of .NET Framework classes, enabling the Visual Basic user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="fa8d6-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="fa8d6-113">MyBase</span></span>  
 <span data-ttu-id="fa8d6-114">@No__t-0 キーワードは、クラスの現在のインスタンスの基底クラスを参照するオブジェクト変数のように動作します。</span><span class="sxs-lookup"><span data-stu-id="fa8d6-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="fa8d6-115">`MyBase` は、派生クラスでオーバーライドまたはシャドウされる基底クラスのメンバーにアクセスするためによく使用されます。</span><span class="sxs-lookup"><span data-stu-id="fa8d6-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="fa8d6-116">`MyBase.New` は、派生クラスのコンストラクターから基底クラスのコンストラクターを明示的に呼び出すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="fa8d6-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="fa8d6-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="fa8d6-117">MyClass</span></span>  
 <span data-ttu-id="fa8d6-118">@No__t-0 キーワードは、もともと実装されているクラスの現在のインスタンスを参照するオブジェクト変数のように動作します。</span><span class="sxs-lookup"><span data-stu-id="fa8d6-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="fa8d6-119">`MyClass` は `Me` に似ていますが、このメソッドのすべてのメソッド呼び出しは、メソッドが @no__t であるかのように処理されます。</span><span class="sxs-lookup"><span data-stu-id="fa8d6-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa8d6-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa8d6-120">See also</span></span>

- [<span data-ttu-id="fa8d6-121">継承の基本</span><span class="sxs-lookup"><span data-stu-id="fa8d6-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
