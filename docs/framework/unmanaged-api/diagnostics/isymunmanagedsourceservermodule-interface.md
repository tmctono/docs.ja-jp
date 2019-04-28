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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ba81c208c4b49342c6a055e09ba898871db1851
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922136"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="82544-102">ISymUnmanagedSourceServerModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="82544-102">ISymUnmanagedSourceServerModule Interface</span></span>
<span data-ttu-id="82544-103">モジュールのソース サーバーのデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="82544-103">Provides source server data for a module.</span></span> <span data-ttu-id="82544-104">このインターフェイスを呼び出すことによって取得`QueryInterface`を実装するオブジェクトで、 [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="82544-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="82544-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="82544-105">Methods</span></span>  
  
|<span data-ttu-id="82544-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="82544-106">Method</span></span>|<span data-ttu-id="82544-107">説明</span><span class="sxs-lookup"><span data-stu-id="82544-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="82544-108">GetSourceServerData メソッド</span><span class="sxs-lookup"><span data-stu-id="82544-108">GetSourceServerData Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="82544-109">モジュールのソース サーバーのデータを返します。</span><span class="sxs-lookup"><span data-stu-id="82544-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="82544-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="82544-110">Requirements</span></span>  
 <span data-ttu-id="82544-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="82544-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82544-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="82544-112">See also</span></span>

- [<span data-ttu-id="82544-113">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="82544-113">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
