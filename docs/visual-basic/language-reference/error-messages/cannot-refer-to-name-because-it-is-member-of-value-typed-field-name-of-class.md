---
title: "'<name>' は、'System.MarshalByRefObject' を基本クラスとして持つクラス '<name>' の値付きフィールド '<classname>' のメンバーであるため、参照できません。"
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: 78b0a3131b6e77ed257f200523ecebd4dfce3691
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61649934"
---
# <a name="cannot-refer-to-name-because-it-is-a-member-of-the-value-typed-field-name-of-class-classname-which-has-systemmarshalbyrefobject-as-a-base-class"></a><span data-ttu-id="04163-102">参照できません '\<名 >' の値に型指定されたフィールドのメンバーであるため、'\<名 >' のクラスの\<classname >' 'system.marshalbyrefobject'' 基底クラスとして</span><span class="sxs-lookup"><span data-stu-id="04163-102">Cannot refer to '\<name>' because it is a member of the value-typed field '\<name>' of class '\<classname>' which has 'System.MarshalByRefObject' as a base class</span></span>
<span data-ttu-id="04163-103">`System.MarshalByRefObject`クラスは、アプリケーション ドメイン境界を越えてオブジェクトへのリモート アクセスをサポートするアプリケーションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="04163-103">The `System.MarshalByRefObject` class enables applications that support remote access to objects across application domain boundaries.</span></span> <span data-ttu-id="04163-104">型を継承する必要があります、`MarshalByRejectObject`クラスの型がアプリケーション ドメイン境界を越えて使用するとします。</span><span class="sxs-lookup"><span data-stu-id="04163-104">Types must inherit from the `MarshalByRejectObject` class when the type is used across application domain boundaries.</span></span> <span data-ttu-id="04163-105">オブジェクトのメンバーが作成されたアプリケーション ドメインの外部で使用できないために、オブジェクトの状態はコピーされませんする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04163-105">The state of the object must not be copied because the members of the object are not usable outside the application domain in which they were created.</span></span>  
  
 <span data-ttu-id="04163-106">**エラー ID:** BC30310</span><span class="sxs-lookup"><span data-stu-id="04163-106">**Error ID:** BC30310</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="04163-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="04163-107">To correct this error</span></span>  
  
1. <span data-ttu-id="04163-108">参照先のメンバーが有効かどうかを確認への参照を確認してください。</span><span class="sxs-lookup"><span data-stu-id="04163-108">Check the reference to make sure the member being referred to is valid.</span></span>  
  
2. <span data-ttu-id="04163-109">持つメンバーを明示的に修飾、`Me`キーワード。</span><span class="sxs-lookup"><span data-stu-id="04163-109">Explicitly qualify the member with the `Me` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04163-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="04163-110">See also</span></span>

- <xref:System.MarshalByRefObject>
- [<span data-ttu-id="04163-111">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="04163-111">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
