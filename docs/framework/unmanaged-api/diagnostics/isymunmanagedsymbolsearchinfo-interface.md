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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61944572"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="8144d-102">ISymUnmanagedSymbolSearchInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8144d-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="8144d-103">検索パスに関する情報を取得するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="8144d-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="8144d-104">このインターフェイスを呼び出すことによって取得`QueryInterface`を実装するオブジェクトで、 [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="8144d-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8144d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="8144d-105">Methods</span></span>  
  
|<span data-ttu-id="8144d-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="8144d-106">Method</span></span>|<span data-ttu-id="8144d-107">説明</span><span class="sxs-lookup"><span data-stu-id="8144d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8144d-108">GetHRESULT メソッド</span><span class="sxs-lookup"><span data-stu-id="8144d-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="8144d-109">HRESULT を取得します。</span><span class="sxs-lookup"><span data-stu-id="8144d-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="8144d-110">GetSearchPath メソッド</span><span class="sxs-lookup"><span data-stu-id="8144d-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="8144d-111">検索パスを取得します。</span><span class="sxs-lookup"><span data-stu-id="8144d-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="8144d-112">GetSearchPathLength メソッド</span><span class="sxs-lookup"><span data-stu-id="8144d-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="8144d-113">検索パスの長さを取得します。</span><span class="sxs-lookup"><span data-stu-id="8144d-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8144d-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="8144d-114">Requirements</span></span>  
 <span data-ttu-id="8144d-115">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8144d-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8144d-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="8144d-116">See also</span></span>

- [<span data-ttu-id="8144d-117">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8144d-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
