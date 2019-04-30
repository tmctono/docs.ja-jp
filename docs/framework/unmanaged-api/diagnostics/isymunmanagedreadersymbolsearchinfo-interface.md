---
title: ISymUnmanagedReaderSymbolSearchInfo インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedReaderSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: fde7e21d-1169-4bed-a34d-792e69652bf9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a872774b1c4510c8d0325c59ae7678c867c1aff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986233"
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a><span data-ttu-id="05563-102">ISymUnmanagedReaderSymbolSearchInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="05563-102">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>
<span data-ttu-id="05563-103">シンボルの検索情報を取得するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="05563-103">Provides methods that get symbol search information.</span></span> <span data-ttu-id="05563-104">このインターフェイスを呼び出すことによって取得`QueryInterface`を実装するオブジェクトで、 [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="05563-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05563-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="05563-105">Methods</span></span>  
  
|<span data-ttu-id="05563-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="05563-106">Method</span></span>|<span data-ttu-id="05563-107">説明</span><span class="sxs-lookup"><span data-stu-id="05563-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="05563-108">GetSymbolSearchInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="05563-108">GetSymbolSearchInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|<span data-ttu-id="05563-109">シンボルの検索情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="05563-109">Gets symbol search information.</span></span>|  
|[<span data-ttu-id="05563-110">GetSymbolSearchInfoCount メソッド</span><span class="sxs-lookup"><span data-stu-id="05563-110">GetSymbolSearchInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|<span data-ttu-id="05563-111">シンボルの検索情報の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="05563-111">Gets a count of symbol search information.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="05563-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="05563-112">Requirements</span></span>  
 <span data-ttu-id="05563-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="05563-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05563-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="05563-114">See also</span></span>

- [<span data-ttu-id="05563-115">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="05563-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
