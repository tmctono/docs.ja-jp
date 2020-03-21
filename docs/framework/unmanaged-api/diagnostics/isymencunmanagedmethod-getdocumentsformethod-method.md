---
title: ISymENCUnmanagedMethod::GetDocumentsForMethod メソッド
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethod
helpviewer_keywords:
- GetDocumentsForMethod method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethod method [.NET Framework debugging]
ms.assetid: bd6ccde5-d578-48d8-abed-b474fbd48d13
topic_type:
- apiref
ms.openlocfilehash: 97f0d81c389ffd0bd8a69df2ca39322d726f98bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176631"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="3787b-102">ISymENCUnmanagedMethod::GetDocumentsForMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="3787b-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="3787b-103">このメソッドに行があるドキュメントを取得します。</span><span class="sxs-lookup"><span data-stu-id="3787b-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3787b-104">構文</span><span class="sxs-lookup"><span data-stu-id="3787b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3787b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3787b-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="3787b-106">[in]が`pcDocs`指すバッファの長さ。</span><span class="sxs-lookup"><span data-stu-id="3787b-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="3787b-107">[アウト]ドキュメントを`ULONG32`格納するために必要なバッファーのサイズ (文字数) を受け取るを指すポインター。</span><span class="sxs-lookup"><span data-stu-id="3787b-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="3787b-108">[in]ドキュメントを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="3787b-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3787b-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="3787b-109">Return Value</span></span>  
 <span data-ttu-id="3787b-110">メソッドが成功した場合はS_OK。それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="3787b-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3787b-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="3787b-111">Requirements</span></span>  
 <span data-ttu-id="3787b-112">**ヘッダー:** コーシム.idl,コーシム.h</span><span class="sxs-lookup"><span data-stu-id="3787b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3787b-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="3787b-113">See also</span></span>

- [<span data-ttu-id="3787b-114">ISymENCUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3787b-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
