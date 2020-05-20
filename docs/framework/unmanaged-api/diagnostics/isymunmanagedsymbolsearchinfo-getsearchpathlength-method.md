---
title: ISymUnmanagedSymbolSearchInfo::GetSearchPathLength メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPathLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength
helpviewer_keywords:
- GetSearchPathLength method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength method [.NET Framework debugging]
ms.assetid: 274e73cf-8333-47ba-ac12-70214e2b0112
topic_type:
- apiref
ms.openlocfilehash: 0be7297fbb71302035e71fbbf2c8b5e2a7faa2da
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615294"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="d44fc-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength メソッド</span><span class="sxs-lookup"><span data-stu-id="d44fc-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="d44fc-103">検索パスの長さを取得します。</span><span class="sxs-lookup"><span data-stu-id="d44fc-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d44fc-104">構文</span><span class="sxs-lookup"><span data-stu-id="d44fc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d44fc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d44fc-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="d44fc-106">入出力`ULONG32`検索パスの長さを格納するために必要なバッファーのサイズ (文字数) を受け取るへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d44fc-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d44fc-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="d44fc-107">Return Value</span></span>  
 <span data-ttu-id="d44fc-108">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="d44fc-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d44fc-109">要件</span><span class="sxs-lookup"><span data-stu-id="d44fc-109">Requirements</span></span>  
 <span data-ttu-id="d44fc-110">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="d44fc-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d44fc-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="d44fc-111">See also</span></span>

- [<span data-ttu-id="d44fc-112">ISymUnmanagedSymbolSearchInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d44fc-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
