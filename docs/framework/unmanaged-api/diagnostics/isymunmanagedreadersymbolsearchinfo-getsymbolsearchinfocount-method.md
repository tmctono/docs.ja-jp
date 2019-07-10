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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c1a72f76f1cd6f6571eaebff3a8046de8dcd3d74
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751459"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfocount-method"></a><span data-ttu-id="de5c0-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount メソッド</span><span class="sxs-lookup"><span data-stu-id="de5c0-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount Method</span></span>
<span data-ttu-id="de5c0-103">シンボルの検索情報の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="de5c0-103">Gets a count of symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de5c0-104">構文</span><span class="sxs-lookup"><span data-stu-id="de5c0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfoCount(  
    [out] ULONG32 *pcSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de5c0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="de5c0-105">Parameters</span></span>  
 `pcSearchInfo`  
 <span data-ttu-id="de5c0-106">out] へのポインター、`ULONG32`検索情報の格納に必要なバッファーのサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="de5c0-106">]out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de5c0-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="de5c0-107">Return Value</span></span>  
 <span data-ttu-id="de5c0-108">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="de5c0-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de5c0-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="de5c0-109">Requirements</span></span>  
 <span data-ttu-id="de5c0-110">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="de5c0-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de5c0-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="de5c0-111">See also</span></span>

- [<span data-ttu-id="de5c0-112">ISymUnmanagedReaderSymbolSearchInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de5c0-112">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
