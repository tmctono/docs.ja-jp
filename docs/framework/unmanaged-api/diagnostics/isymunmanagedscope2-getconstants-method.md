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
ms.openlocfilehash: 45268929b6e9ad6ac6423aa0fa2b7b5022bc9179
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176618"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="a6c82-102">ISymUnmanagedScope2::GetConstants メソッド</span><span class="sxs-lookup"><span data-stu-id="a6c82-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="a6c82-103">このスコープ内で定義されているローカル定数を取得します。</span><span class="sxs-lookup"><span data-stu-id="a6c82-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6c82-104">構文</span><span class="sxs-lookup"><span data-stu-id="a6c82-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*
             constants[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6c82-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a6c82-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="a6c82-106">[in]パラメーターが指すバッファーの`pcConstants`長さ。</span><span class="sxs-lookup"><span data-stu-id="a6c82-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="a6c82-107">[アウト]定数を`ULONG32`格納するために必要なバッファーのサイズ (文字数) を受け取るを指すポインター。</span><span class="sxs-lookup"><span data-stu-id="a6c82-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="a6c82-108">[アウト]定数を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="a6c82-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6c82-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="a6c82-109">Return Value</span></span>  
 <span data-ttu-id="a6c82-110">メソッドが成功した場合はS_OK。それ以外の場合は、E_FAILまたはその他のエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="a6c82-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6c82-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="a6c82-111">Requirements</span></span>  
 <span data-ttu-id="a6c82-112">**ヘッダー:** コーシム.idl,コーシム.h</span><span class="sxs-lookup"><span data-stu-id="a6c82-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6c82-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6c82-113">See also</span></span>

- [<span data-ttu-id="a6c82-114">ISymUnmanagedScope2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6c82-114">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
