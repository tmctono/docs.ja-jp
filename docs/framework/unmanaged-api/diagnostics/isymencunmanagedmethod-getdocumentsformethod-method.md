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
ms.openlocfilehash: 89be772ee3d8a6fc5acb74d5ebe6d3c691764f89
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441956"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="cdbbc-102">ISymENCUnmanagedMethod::GetDocumentsForMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="cdbbc-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="cdbbc-103">このメソッドに行が含まれているドキュメントを取得します。</span><span class="sxs-lookup"><span data-stu-id="cdbbc-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdbbc-104">構文</span><span class="sxs-lookup"><span data-stu-id="cdbbc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdbbc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cdbbc-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="cdbbc-106">からが指すバッファーの長さ `pcDocs` 。</span><span class="sxs-lookup"><span data-stu-id="cdbbc-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="cdbbc-107">入出力`ULONG32`ドキュメントを格納するために必要なバッファーのサイズ (文字数) を受け取るへのポインター。</span><span class="sxs-lookup"><span data-stu-id="cdbbc-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="cdbbc-108">からドキュメントを格納しているバッファー。</span><span class="sxs-lookup"><span data-stu-id="cdbbc-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cdbbc-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="cdbbc-109">Return Value</span></span>  
 <span data-ttu-id="cdbbc-110">メソッドが成功した場合は S_OK。それ以外の場合は、エラーコード。</span><span class="sxs-lookup"><span data-stu-id="cdbbc-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdbbc-111">要件</span><span class="sxs-lookup"><span data-stu-id="cdbbc-111">Requirements</span></span>  
 <span data-ttu-id="cdbbc-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="cdbbc-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdbbc-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="cdbbc-113">See also</span></span>

- [<span data-ttu-id="cdbbc-114">ISymENCUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cdbbc-114">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
