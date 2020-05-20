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
ms.openlocfilehash: 3f6cea68a4379f8769ccbdbc6911cc5c425d3369
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614878"
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a><span data-ttu-id="0d97a-102">ISymUnmanagedReaderSymbolSearchInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0d97a-102">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>
<span data-ttu-id="0d97a-103">シンボル検索情報を取得するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="0d97a-103">Provides methods that get symbol search information.</span></span> <span data-ttu-id="0d97a-104">このインターフェイスを取得するには `QueryInterface` 、 [ISymUnmanagedReader](isymunmanagedreader-interface.md)インターフェイスを実装するオブジェクトに対してを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0d97a-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0d97a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="0d97a-105">Methods</span></span>  
  
|<span data-ttu-id="0d97a-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="0d97a-106">Method</span></span>|<span data-ttu-id="0d97a-107">説明</span><span class="sxs-lookup"><span data-stu-id="0d97a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d97a-108">GetSymbolSearchInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="0d97a-108">GetSymbolSearchInfo Method</span></span>](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|<span data-ttu-id="0d97a-109">シンボルの検索情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="0d97a-109">Gets symbol search information.</span></span>|  
|[<span data-ttu-id="0d97a-110">GetSymbolSearchInfoCount メソッド</span><span class="sxs-lookup"><span data-stu-id="0d97a-110">GetSymbolSearchInfoCount Method</span></span>](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|<span data-ttu-id="0d97a-111">シンボル検索情報の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="0d97a-111">Gets a count of symbol search information.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0d97a-112">要件</span><span class="sxs-lookup"><span data-stu-id="0d97a-112">Requirements</span></span>  
 <span data-ttu-id="0d97a-113">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="0d97a-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d97a-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d97a-114">See also</span></span>

- [<span data-ttu-id="0d97a-115">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0d97a-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
