---
title: ISymUnmanagedReader::GetMethod メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedReader interface [.NET Framework debugging]
- ISymUnmanagedReader::GetMethod method [.NET Framework debugging]
ms.assetid: ae6cfb29-bc2c-4606-af86-1d32ebd31020
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 031e51919d9abd7092756cc42fb35dcc0592758c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503048"
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="44c9c-102">ISymUnmanagedReader::GetMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="44c9c-102">ISymUnmanagedReader::GetMethod Method</span></span>
<span data-ttu-id="44c9c-103">シンボル リーダー メソッドでは、指定したメソッドのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="44c9c-103">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44c9c-104">構文</span><span class="sxs-lookup"><span data-stu-id="44c9c-104">Syntax</span></span>  
  
```  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44c9c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="44c9c-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="44c9c-106">[in]メソッド トークンです。</span><span class="sxs-lookup"><span data-stu-id="44c9c-106">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="44c9c-107">[out]返されたインターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="44c9c-107">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44c9c-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="44c9c-108">Return Value</span></span>  
 <span data-ttu-id="44c9c-109">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="44c9c-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44c9c-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="44c9c-110">Requirements</span></span>  
 <span data-ttu-id="44c9c-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="44c9c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44c9c-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="44c9c-112">See also</span></span>
- [<span data-ttu-id="44c9c-113">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="44c9c-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
