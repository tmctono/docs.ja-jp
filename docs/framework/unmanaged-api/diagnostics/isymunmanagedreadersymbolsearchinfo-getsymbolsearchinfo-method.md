---
title: ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo
helpviewer_keywords:
- GetSymbolSearchInfo method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo method [.NET Framework debugging]
ms.assetid: 40fcdbc5-3bb2-41e9-b995-40984c209a7f
topic_type:
- apiref
ms.openlocfilehash: 2b5a42c89e0e3efed61b1b471c227e0df85a51aa
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614904"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="1ce52-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="1ce52-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>
<span data-ttu-id="1ce52-103">シンボルの検索情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="1ce52-103">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ce52-104">構文</span><span class="sxs-lookup"><span data-stu-id="1ce52-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ce52-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1ce52-105">Parameters</span></span>  
 `cSearchInfo`  
 <span data-ttu-id="1ce52-106">から`ULONG32`のサイズを示す `rgpSearchInfo` です。</span><span class="sxs-lookup"><span data-stu-id="1ce52-106">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="1ce52-107">入出力`ULONG32`検索情報を格納するために必要なバッファーのサイズを受け取るへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1ce52-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="1ce52-108">入出力返された[ISymUnmanagedSymbolSearchInfo](isymunmanagedsymbolsearchinfo-interface.md)インターフェイスに設定されたポインター。</span><span class="sxs-lookup"><span data-stu-id="1ce52-108">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ce52-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="1ce52-109">Return Value</span></span>  
 <span data-ttu-id="1ce52-110">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="1ce52-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ce52-111">要件</span><span class="sxs-lookup"><span data-stu-id="1ce52-111">Requirements</span></span>  
 <span data-ttu-id="1ce52-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="1ce52-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ce52-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ce52-113">See also</span></span>

- [<span data-ttu-id="1ce52-114">ISymUnmanagedReaderSymbolSearchInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1ce52-114">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)
