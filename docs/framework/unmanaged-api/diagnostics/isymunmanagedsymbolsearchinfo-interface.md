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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d573264bb7a3cac02dd41afacaa2bc4a6f9e6dcd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207553"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="78731-102">ISymUnmanagedSymbolSearchInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="78731-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="78731-103">検索パスに関する情報を取得するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="78731-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="78731-104">このインターフェイスを呼び出すことによって取得`QueryInterface`を実装するオブジェクトで、 [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="78731-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="78731-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="78731-105">Methods</span></span>  
  
|<span data-ttu-id="78731-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="78731-106">Method</span></span>|<span data-ttu-id="78731-107">説明</span><span class="sxs-lookup"><span data-stu-id="78731-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="78731-108">GetHRESULT メソッド</span><span class="sxs-lookup"><span data-stu-id="78731-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="78731-109">HRESULT を取得します。</span><span class="sxs-lookup"><span data-stu-id="78731-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="78731-110">GetSearchPath メソッド</span><span class="sxs-lookup"><span data-stu-id="78731-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="78731-111">検索パスを取得します。</span><span class="sxs-lookup"><span data-stu-id="78731-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="78731-112">GetSearchPathLength メソッド</span><span class="sxs-lookup"><span data-stu-id="78731-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="78731-113">検索パスの長さを取得します。</span><span class="sxs-lookup"><span data-stu-id="78731-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="78731-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="78731-114">Requirements</span></span>  
 <span data-ttu-id="78731-115">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="78731-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78731-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="78731-116">See also</span></span>

- [<span data-ttu-id="78731-117">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="78731-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
