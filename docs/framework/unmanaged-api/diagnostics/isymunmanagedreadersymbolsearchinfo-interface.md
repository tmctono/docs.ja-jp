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
ms.openlocfilehash: e97dc1d06eb4f5eb110923db20896d7d12c41710
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446379"
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a><span data-ttu-id="b2bc6-102">ISymUnmanagedReaderSymbolSearchInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b2bc6-102">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>
<span data-ttu-id="b2bc6-103">シンボル検索情報を取得するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="b2bc6-103">Provides methods that get symbol search information.</span></span> <span data-ttu-id="b2bc6-104">このインターフェイスを取得するには、 [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)インターフェイスを実装するオブジェクトで `QueryInterface` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b2bc6-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b2bc6-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b2bc6-105">Methods</span></span>  
  
|<span data-ttu-id="b2bc6-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="b2bc6-106">Method</span></span>|<span data-ttu-id="b2bc6-107">説明</span><span class="sxs-lookup"><span data-stu-id="b2bc6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b2bc6-108">GetSymbolSearchInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="b2bc6-108">GetSymbolSearchInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|<span data-ttu-id="b2bc6-109">シンボルの検索情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="b2bc6-109">Gets symbol search information.</span></span>|  
|[<span data-ttu-id="b2bc6-110">GetSymbolSearchInfoCount メソッド</span><span class="sxs-lookup"><span data-stu-id="b2bc6-110">GetSymbolSearchInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|<span data-ttu-id="b2bc6-111">シンボル検索情報の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="b2bc6-111">Gets a count of symbol search information.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2bc6-112">要件</span><span class="sxs-lookup"><span data-stu-id="b2bc6-112">Requirements</span></span>  
 <span data-ttu-id="b2bc6-113">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="b2bc6-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2bc6-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2bc6-114">See also</span></span>

- [<span data-ttu-id="b2bc6-115">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b2bc6-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
