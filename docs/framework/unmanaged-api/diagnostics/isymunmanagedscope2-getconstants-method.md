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
ms.openlocfilehash: bb3f5926677577bbc0bb14413c5d70150ef25152
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778043"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="7c4d7-102">ISymUnmanagedScope2::GetConstants メソッド</span><span class="sxs-lookup"><span data-stu-id="7c4d7-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="7c4d7-103">このスコープ内で定義されているローカル定数を取得します。</span><span class="sxs-lookup"><span data-stu-id="7c4d7-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c4d7-104">構文</span><span class="sxs-lookup"><span data-stu-id="7c4d7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*   
             constants[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c4d7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7c4d7-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="7c4d7-106">[in]バッファーの長さを`pcConstants`パラメーターを指します。</span><span class="sxs-lookup"><span data-stu-id="7c4d7-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="7c4d7-107">[out]ポインター、`ULONG32`文字定数の格納に必要なバッファーのサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="7c4d7-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="7c4d7-108">[out]定数を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="7c4d7-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c4d7-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="7c4d7-109">Return Value</span></span>  
 <span data-ttu-id="7c4d7-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="7c4d7-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c4d7-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="7c4d7-111">Requirements</span></span>  
 <span data-ttu-id="7c4d7-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7c4d7-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c4d7-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c4d7-113">See also</span></span>

- [<span data-ttu-id="7c4d7-114">ISymUnmanagedScope2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c4d7-114">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
