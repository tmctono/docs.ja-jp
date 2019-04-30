---
title: ISymUnmanagedWriter::RemapToken メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.RemapToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 979d14b4c404c3bf12c427bd5b8b1d4997805e7b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986012"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="c9e0a-102">ISymUnmanagedWriter::RemapToken メソッド</span><span class="sxs-lookup"><span data-stu-id="c9e0a-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="c9e0a-103">メタデータ トークンが再マップされたメタデータの生成とするシンボルのライターに通知します。</span><span class="sxs-lookup"><span data-stu-id="c9e0a-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="c9e0a-104">シンボルのライターがシンボル ストア内の古いトークンを格納してある場合、読み込みフェーズ中に再マップする対応するシンボル リーダーのマップを保存して格納したトークンを新しい値、またはそのどちらかの更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9e0a-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9e0a-105">構文</span><span class="sxs-lookup"><span data-stu-id="c9e0a-105">Syntax</span></span>  
  
```  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9e0a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c9e0a-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="c9e0a-107">[in]再マップされたメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="c9e0a-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="c9e0a-108">[in]新しいメタデータ トークンを`oldToken`が再マップします。</span><span class="sxs-lookup"><span data-stu-id="c9e0a-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9e0a-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="c9e0a-109">Return Value</span></span>  
 <span data-ttu-id="c9e0a-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="c9e0a-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9e0a-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="c9e0a-111">Requirements</span></span>  
 <span data-ttu-id="c9e0a-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c9e0a-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9e0a-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9e0a-113">See also</span></span>

- [<span data-ttu-id="c9e0a-114">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c9e0a-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
