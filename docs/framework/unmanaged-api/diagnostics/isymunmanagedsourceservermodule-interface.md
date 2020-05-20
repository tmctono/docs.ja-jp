---
title: ISymUnmanagedSourceServerModule インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule
helpviewer_keywords:
- ISymUnmanagedSourceServerModule interface [.NET Framework debugging]
ms.assetid: a19b23bd-2061-476e-b67d-252f57404f8b
topic_type:
- apiref
ms.openlocfilehash: d90a55b53ba00540137e44fc190790c4710903e3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610796"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="9e299-102">ISymUnmanagedSourceServerModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e299-102">ISymUnmanagedSourceServerModule Interface</span></span>
<span data-ttu-id="9e299-103">モジュールのソースサーバーデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="9e299-103">Provides source server data for a module.</span></span> <span data-ttu-id="9e299-104">このインターフェイスを取得するには `QueryInterface` 、 [ISymUnmanagedReader](isymunmanagedreader-interface.md)インターフェイスを実装するオブジェクトに対してを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9e299-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9e299-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="9e299-105">Methods</span></span>  
  
|<span data-ttu-id="9e299-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="9e299-106">Method</span></span>|<span data-ttu-id="9e299-107">説明</span><span class="sxs-lookup"><span data-stu-id="9e299-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9e299-108">GetSourceServerData メソッド</span><span class="sxs-lookup"><span data-stu-id="9e299-108">GetSourceServerData Method</span></span>](isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="9e299-109">モジュールのソースサーバーデータを返します。</span><span class="sxs-lookup"><span data-stu-id="9e299-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9e299-110">要件</span><span class="sxs-lookup"><span data-stu-id="9e299-110">Requirements</span></span>  
 <span data-ttu-id="9e299-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="9e299-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e299-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e299-112">See also</span></span>

- [<span data-ttu-id="9e299-113">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e299-113">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
