---
title: ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfoCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount
helpviewer_keywords:
- GetSymbolSearchInfoCount method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount method [.NET Framework debugging]
ms.assetid: 4068b6ec-525f-4446-8818-0296178cbd19
topic_type:
- apiref
ms.openlocfilehash: a81a5afeec8f97864e1772347c6575b9d09cb176
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614891"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfocount-method"></a><span data-ttu-id="505ce-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount メソッド</span><span class="sxs-lookup"><span data-stu-id="505ce-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount Method</span></span>
<span data-ttu-id="505ce-103">シンボル検索情報の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="505ce-103">Gets a count of symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="505ce-104">構文</span><span class="sxs-lookup"><span data-stu-id="505ce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfoCount(  
    [out] ULONG32 *pcSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="505ce-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="505ce-105">Parameters</span></span>  
 `pcSearchInfo`  
 <span data-ttu-id="505ce-106">] out] `ULONG32` 検索情報を格納するために必要なバッファーのサイズを受け取るへのポインター。</span><span class="sxs-lookup"><span data-stu-id="505ce-106">]out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="505ce-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="505ce-107">Return Value</span></span>  
 <span data-ttu-id="505ce-108">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="505ce-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="505ce-109">要件</span><span class="sxs-lookup"><span data-stu-id="505ce-109">Requirements</span></span>  
 <span data-ttu-id="505ce-110">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="505ce-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="505ce-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="505ce-111">See also</span></span>

- [<span data-ttu-id="505ce-112">ISymUnmanagedReaderSymbolSearchInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="505ce-112">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)
