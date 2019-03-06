---
title: ISymENCUnmanagedMethod::GetSourceExtentInDocument メソッド
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetSourceExtentInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetSourceExtentInDocument
helpviewer_keywords:
- GetSourceExtentInDocument method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetSourceExtentInDocument method [.NET Framework debugging]
ms.assetid: 9c5566ab-4ec7-4b61-9753-839bb90ae78c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5f29111fd68d9a47cd90687cc6aa2743968e727d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484603"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a><span data-ttu-id="7e43d-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument メソッド</span><span class="sxs-lookup"><span data-stu-id="7e43d-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument Method</span></span>
<span data-ttu-id="7e43d-103">取得では、特定のドキュメントでメソッドの最大の終了行と行を最小を開始します。</span><span class="sxs-lookup"><span data-stu-id="7e43d-103">Gets the smallest start line and largest end line for the method in a specific document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e43d-104">構文</span><span class="sxs-lookup"><span data-stu-id="7e43d-104">Syntax</span></span>  
  
```  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e43d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7e43d-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="7e43d-106">[in]ドキュメントへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7e43d-106">[in] A pointer to the document.</span></span>  
  
 `pstartLine`  
 <span data-ttu-id="7e43d-107">[out]ポインターを`ULONG32`開始行を受け取る。</span><span class="sxs-lookup"><span data-stu-id="7e43d-107">[out] A pointer to a `ULONG32` that receives the start line.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="7e43d-108">[out]ポインター、`ULONG32`最終行を受け取る。</span><span class="sxs-lookup"><span data-stu-id="7e43d-108">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e43d-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="7e43d-109">Return Value</span></span>  
 <span data-ttu-id="7e43d-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="7e43d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e43d-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="7e43d-111">Requirements</span></span>  
 <span data-ttu-id="7e43d-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7e43d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e43d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e43d-113">See also</span></span>
- [<span data-ttu-id="7e43d-114">ISymENCUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7e43d-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
