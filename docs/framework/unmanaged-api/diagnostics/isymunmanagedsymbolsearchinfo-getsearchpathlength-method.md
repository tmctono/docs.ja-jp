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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 27de34c1978818c48d5fa38caf9b52ff2a9510f5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778085"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="0dc69-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength メソッド</span><span class="sxs-lookup"><span data-stu-id="0dc69-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="0dc69-103">検索パスの長さを取得します。</span><span class="sxs-lookup"><span data-stu-id="0dc69-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dc69-104">構文</span><span class="sxs-lookup"><span data-stu-id="0dc69-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0dc69-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0dc69-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="0dc69-106">[out]ポインター、`ULONG32`検索パスの長さを格納するために必要なバッファーの文字のサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="0dc69-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0dc69-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="0dc69-107">Return Value</span></span>  
 <span data-ttu-id="0dc69-108">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="0dc69-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dc69-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="0dc69-109">Requirements</span></span>  
 <span data-ttu-id="0dc69-110">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0dc69-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dc69-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="0dc69-111">See also</span></span>

- [<span data-ttu-id="0dc69-112">ISymUnmanagedSymbolSearchInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0dc69-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
