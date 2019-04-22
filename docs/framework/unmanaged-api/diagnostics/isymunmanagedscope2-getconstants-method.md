---
title: ISymUnmanagedScope2::GetConstants メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstants
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstants
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstants method [.NET Framework debugging]
- GetConstants method [.NET Framework debugging]
ms.assetid: f241b620-9ec5-42fd-92ef-3b22329db72a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 08bc85c7a5b53c145375ca34f11ec499e5e7528f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096824"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="0b536-102">ISymUnmanagedScope2::GetConstants メソッド</span><span class="sxs-lookup"><span data-stu-id="0b536-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="0b536-103">このスコープ内で定義されているローカル定数を取得します。</span><span class="sxs-lookup"><span data-stu-id="0b536-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b536-104">構文</span><span class="sxs-lookup"><span data-stu-id="0b536-104">Syntax</span></span>  
  
```  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*   
             constants[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b536-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0b536-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="0b536-106">[in]バッファーの長さを`pcConstants`パラメーターを指します。</span><span class="sxs-lookup"><span data-stu-id="0b536-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="0b536-107">[out]ポインター、`ULONG32`文字定数の格納に必要なバッファーのサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="0b536-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="0b536-108">[out]定数を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="0b536-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b536-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="0b536-109">Return Value</span></span>  
 <span data-ttu-id="0b536-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="0b536-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b536-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="0b536-111">Requirements</span></span>  
 <span data-ttu-id="0b536-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0b536-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b536-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b536-113">See also</span></span>

- [<span data-ttu-id="0b536-114">ISymUnmanagedScope2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0b536-114">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
