---
title: ISymUnmanagedScope2::GetConstantCount メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstantCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstantCount
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstantCount method [.NET Framework debugging]
- GetConstantCount method [.NET Framework debugging]
ms.assetid: 1e1f0be6-c4e8-4d6c-98cd-d5fa9f686e87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a063d25e180be466421c14ca65a5b4cea881fc8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761620"
---
# <a name="isymunmanagedscope2getconstantcount-method"></a><span data-ttu-id="c61de-102">ISymUnmanagedScope2::GetConstantCount メソッド</span><span class="sxs-lookup"><span data-stu-id="c61de-102">ISymUnmanagedScope2::GetConstantCount Method</span></span>
<span data-ttu-id="c61de-103">このスコープ内で定義されている定数の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="c61de-103">Gets a count of the constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c61de-104">構文</span><span class="sxs-lookup"><span data-stu-id="c61de-104">Syntax</span></span>  
  
```  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c61de-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c61de-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="c61de-106">[out]ポインター、`ULONG32`文字定数の格納に必要なバッファーのサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="c61de-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c61de-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="c61de-107">Return Value</span></span>  
 <span data-ttu-id="c61de-108">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="c61de-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c61de-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="c61de-109">Requirements</span></span>  
 <span data-ttu-id="c61de-110">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c61de-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c61de-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="c61de-111">See also</span></span>

- [<span data-ttu-id="c61de-112">ISymUnmanagedScope2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c61de-112">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
