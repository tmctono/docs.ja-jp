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
ms.openlocfilehash: 37e9926c8f9677e3b38202c5fb3c43f7b1159edf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170613"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="842cb-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength メソッド</span><span class="sxs-lookup"><span data-stu-id="842cb-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="842cb-103">検索パスの長さを取得します。</span><span class="sxs-lookup"><span data-stu-id="842cb-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="842cb-104">構文</span><span class="sxs-lookup"><span data-stu-id="842cb-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="842cb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="842cb-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="842cb-106">[out]ポインター、`ULONG32`検索パスの長さを格納するために必要なバッファーの文字のサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="842cb-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="842cb-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="842cb-107">Return Value</span></span>  
 <span data-ttu-id="842cb-108">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="842cb-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="842cb-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="842cb-109">Requirements</span></span>  
 <span data-ttu-id="842cb-110">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="842cb-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="842cb-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="842cb-111">See also</span></span>

- [<span data-ttu-id="842cb-112">ISymUnmanagedSymbolSearchInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="842cb-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
