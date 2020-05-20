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
ms.openlocfilehash: f558d209d13fae93bd3a6f5e0e653afb91371a6a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615333"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="6a386-102">ISymUnmanagedScope2::GetConstants メソッド</span><span class="sxs-lookup"><span data-stu-id="6a386-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="6a386-103">このスコープ内で定義されているローカル定数を取得します。</span><span class="sxs-lookup"><span data-stu-id="6a386-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a386-104">構文</span><span class="sxs-lookup"><span data-stu-id="6a386-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*
             constants[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a386-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6a386-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="6a386-106">からパラメーターが指すバッファーの長さ `pcConstants` 。</span><span class="sxs-lookup"><span data-stu-id="6a386-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="6a386-107">入出力`ULONG32`定数を格納するために必要なバッファーのサイズ (文字数) を受け取るへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6a386-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="6a386-108">入出力定数を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="6a386-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a386-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="6a386-109">Return Value</span></span>  
 <span data-ttu-id="6a386-110">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a386-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a386-111">要件</span><span class="sxs-lookup"><span data-stu-id="6a386-111">Requirements</span></span>  
 <span data-ttu-id="6a386-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="6a386-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a386-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a386-113">See also</span></span>

- [<span data-ttu-id="6a386-114">ISymUnmanagedScope2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a386-114">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)
