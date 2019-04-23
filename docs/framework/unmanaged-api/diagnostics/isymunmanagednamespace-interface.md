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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 87dd6db9624c2216ab13e77b04cfa63f95aee7e2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183314"
---
# <a name="isymunmanagednamespace-interface"></a><span data-ttu-id="32f5c-102">ISymUnmanagedNamespace インターフェイス</span><span class="sxs-lookup"><span data-stu-id="32f5c-102">ISymUnmanagedNamespace Interface</span></span>
<span data-ttu-id="32f5c-103">名前空間を表します。</span><span class="sxs-lookup"><span data-stu-id="32f5c-103">Represents a namespace.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="32f5c-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="32f5c-104">Methods</span></span>  
  
|<span data-ttu-id="32f5c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="32f5c-105">Method</span></span>|<span data-ttu-id="32f5c-106">説明</span><span class="sxs-lookup"><span data-stu-id="32f5c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="32f5c-107">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="32f5c-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getname-method.md)|<span data-ttu-id="32f5c-108">この名前空間の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="32f5c-108">Gets the name of this namespace.</span></span>|  
|[<span data-ttu-id="32f5c-109">GetNamespaces メソッド</span><span class="sxs-lookup"><span data-stu-id="32f5c-109">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getnamespaces-method.md)|<span data-ttu-id="32f5c-110">この名前空間の子を取得します。</span><span class="sxs-lookup"><span data-stu-id="32f5c-110">Gets the children of this namespace.</span></span>|  
|[<span data-ttu-id="32f5c-111">GetVariables メソッド</span><span class="sxs-lookup"><span data-stu-id="32f5c-111">GetVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getvariables-method.md)|<span data-ttu-id="32f5c-112">この名前空間内のグローバル スコープで定義されたすべての変数を返します。</span><span class="sxs-lookup"><span data-stu-id="32f5c-112">Returns all variables defined at global scope within this namespace.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="32f5c-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="32f5c-113">Requirements</span></span>  
 <span data-ttu-id="32f5c-114">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="32f5c-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32f5c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="32f5c-115">See also</span></span>

- [<span data-ttu-id="32f5c-116">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="32f5c-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
