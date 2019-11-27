---
title: ISymUnmanagedSymbolSearchInfo インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: 30817373-0a21-49c1-a0c4-8e8daeecb8db
topic_type:
- apiref
ms.openlocfilehash: d7371361b074454e8aa359c49b964193c12f3034
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446150"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="740bd-102">ISymUnmanagedSymbolSearchInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="740bd-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="740bd-103">検索パスに関する情報を取得するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="740bd-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="740bd-104">このインターフェイスを取得するには、 [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)インターフェイスを実装するオブジェクトで `QueryInterface` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="740bd-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="740bd-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="740bd-105">Methods</span></span>  
  
|<span data-ttu-id="740bd-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="740bd-106">Method</span></span>|<span data-ttu-id="740bd-107">説明</span><span class="sxs-lookup"><span data-stu-id="740bd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="740bd-108">GetHRESULT メソッド</span><span class="sxs-lookup"><span data-stu-id="740bd-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="740bd-109">HRESULT を取得します。</span><span class="sxs-lookup"><span data-stu-id="740bd-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="740bd-110">GetSearchPath メソッド</span><span class="sxs-lookup"><span data-stu-id="740bd-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="740bd-111">検索パスを取得します。</span><span class="sxs-lookup"><span data-stu-id="740bd-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="740bd-112">GetSearchPathLength メソッド</span><span class="sxs-lookup"><span data-stu-id="740bd-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="740bd-113">検索パスの長さを取得します。</span><span class="sxs-lookup"><span data-stu-id="740bd-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="740bd-114">要件</span><span class="sxs-lookup"><span data-stu-id="740bd-114">Requirements</span></span>  
 <span data-ttu-id="740bd-115">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="740bd-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="740bd-116">参照</span><span class="sxs-lookup"><span data-stu-id="740bd-116">See also</span></span>

- [<span data-ttu-id="740bd-117">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="740bd-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
