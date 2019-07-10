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
ms.openlocfilehash: 1bb9a444d8e8b674d1f173214d8bac427f24e408
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759399"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="ce39d-102">ISymUnmanagedMethod::GetToken メソッド</span><span class="sxs-lookup"><span data-stu-id="ce39d-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="ce39d-103">このメソッドのメタデータ トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="ce39d-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce39d-104">構文</span><span class="sxs-lookup"><span data-stu-id="ce39d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce39d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ce39d-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="ce39d-106">[out]ポインター、`mdMethodDef`メタデータの格納に必要なバッファーの文字のサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="ce39d-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce39d-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="ce39d-107">Return Value</span></span>  
 <span data-ttu-id="ce39d-108">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="ce39d-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce39d-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="ce39d-109">Requirements</span></span>  
 <span data-ttu-id="ce39d-110">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ce39d-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce39d-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce39d-111">See also</span></span>

- [<span data-ttu-id="ce39d-112">ISymUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ce39d-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
