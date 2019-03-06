---
title: ISymUnmanagedMethod::GetToken メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetToken
helpviewer_keywords:
- ISymUnmanagedMethod::GetToken method [.NET Framework debugging]
- GetToken method, ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: 4effbe95-c36e-4a45-8b2a-ee21339415fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5b0acee31017fd02ac3e51f9e585669b9c90ec48
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57467019"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="b42e1-102">ISymUnmanagedMethod::GetToken メソッド</span><span class="sxs-lookup"><span data-stu-id="b42e1-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="b42e1-103">このメソッドのメタデータ トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="b42e1-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b42e1-104">構文</span><span class="sxs-lookup"><span data-stu-id="b42e1-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b42e1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b42e1-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="b42e1-106">[out]ポインター、`mdMethodDef`メタデータの格納に必要なバッファーの文字のサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="b42e1-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b42e1-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="b42e1-107">Return Value</span></span>  
 <span data-ttu-id="b42e1-108">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="b42e1-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b42e1-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="b42e1-109">Requirements</span></span>  
 <span data-ttu-id="b42e1-110">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b42e1-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b42e1-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="b42e1-111">See also</span></span>
- [<span data-ttu-id="b42e1-112">ISymUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b42e1-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
