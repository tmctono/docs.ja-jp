---
title: ISymUnmanagedNamespace インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace
helpviewer_keywords:
- ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: d42bea4e-5848-4e43-a883-69af7a313ce9
topic_type:
- apiref
ms.openlocfilehash: 3bcb642ac62fb00780a4fda7aaeebaabb386db33
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615073"
---
# <a name="isymunmanagednamespace-interface"></a><span data-ttu-id="6e11d-102">ISymUnmanagedNamespace インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6e11d-102">ISymUnmanagedNamespace Interface</span></span>
<span data-ttu-id="6e11d-103">名前空間を表します。</span><span class="sxs-lookup"><span data-stu-id="6e11d-103">Represents a namespace.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6e11d-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="6e11d-104">Methods</span></span>  
  
|<span data-ttu-id="6e11d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="6e11d-105">Method</span></span>|<span data-ttu-id="6e11d-106">説明</span><span class="sxs-lookup"><span data-stu-id="6e11d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6e11d-107">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="6e11d-107">GetName Method</span></span>](isymunmanagednamespace-getname-method.md)|<span data-ttu-id="6e11d-108">この名前空間の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="6e11d-108">Gets the name of this namespace.</span></span>|  
|[<span data-ttu-id="6e11d-109">GetNamespaces メソッド</span><span class="sxs-lookup"><span data-stu-id="6e11d-109">GetNamespaces Method</span></span>](isymunmanagednamespace-getnamespaces-method.md)|<span data-ttu-id="6e11d-110">この名前空間の子を取得します。</span><span class="sxs-lookup"><span data-stu-id="6e11d-110">Gets the children of this namespace.</span></span>|  
|[<span data-ttu-id="6e11d-111">GetVariables メソッド</span><span class="sxs-lookup"><span data-stu-id="6e11d-111">GetVariables Method</span></span>](isymunmanagednamespace-getvariables-method.md)|<span data-ttu-id="6e11d-112">この名前空間内のグローバルスコープで定義されているすべての変数を返します。</span><span class="sxs-lookup"><span data-stu-id="6e11d-112">Returns all variables defined at global scope within this namespace.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6e11d-113">要件</span><span class="sxs-lookup"><span data-stu-id="6e11d-113">Requirements</span></span>  
 <span data-ttu-id="6e11d-114">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="6e11d-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e11d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e11d-115">See also</span></span>

- [<span data-ttu-id="6e11d-116">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6e11d-116">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
