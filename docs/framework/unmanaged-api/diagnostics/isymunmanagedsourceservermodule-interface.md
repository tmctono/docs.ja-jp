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
ms.openlocfilehash: 9eac87d7627f502b13d805b8c5656e01ac578e7f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446199"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="0387c-102">ISymUnmanagedSourceServerModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0387c-102">ISymUnmanagedSourceServerModule Interface</span></span>
<span data-ttu-id="0387c-103">モジュールのソースサーバーデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="0387c-103">Provides source server data for a module.</span></span> <span data-ttu-id="0387c-104">このインターフェイスを取得するには、 [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)インターフェイスを実装するオブジェクトで `QueryInterface` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0387c-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0387c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="0387c-105">Methods</span></span>  
  
|<span data-ttu-id="0387c-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="0387c-106">Method</span></span>|<span data-ttu-id="0387c-107">説明</span><span class="sxs-lookup"><span data-stu-id="0387c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0387c-108">GetSourceServerData メソッド</span><span class="sxs-lookup"><span data-stu-id="0387c-108">GetSourceServerData Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="0387c-109">モジュールのソースサーバーデータを返します。</span><span class="sxs-lookup"><span data-stu-id="0387c-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0387c-110">要件</span><span class="sxs-lookup"><span data-stu-id="0387c-110">Requirements</span></span>  
 <span data-ttu-id="0387c-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="0387c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0387c-112">参照</span><span class="sxs-lookup"><span data-stu-id="0387c-112">See also</span></span>

- [<span data-ttu-id="0387c-113">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0387c-113">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
