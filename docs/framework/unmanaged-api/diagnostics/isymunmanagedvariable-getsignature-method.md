---
title: ISymUnmanagedVariable::GetSignature メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetSignature method [.NET Framework debugging]
ms.assetid: 78c1ba28-a410-4360-805c-23a95408964a
topic_type:
- apiref
ms.openlocfilehash: 2939d9cf3991a9e0b8f93bb301925b1092eca50e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446045"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="92b01-102">ISymUnmanagedVariable::GetSignature メソッド</span><span class="sxs-lookup"><span data-stu-id="92b01-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="92b01-103">Gets the signature of this variable.</span><span class="sxs-lookup"><span data-stu-id="92b01-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92b01-104">構文</span><span class="sxs-lookup"><span data-stu-id="92b01-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92b01-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="92b01-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="92b01-106">[in] The length of the buffer pointed to by the `sig` parameter.</span><span class="sxs-lookup"><span data-stu-id="92b01-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="92b01-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span><span class="sxs-lookup"><span data-stu-id="92b01-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="92b01-108">[out] The buffer that stores the signature.</span><span class="sxs-lookup"><span data-stu-id="92b01-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92b01-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="92b01-109">Return Value</span></span>  
 <span data-ttu-id="92b01-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="92b01-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92b01-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="92b01-111">Requirements</span></span>  
 <span data-ttu-id="92b01-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="92b01-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92b01-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="92b01-113">See also</span></span>

- [<span data-ttu-id="92b01-114">ISymUnmanagedVariable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="92b01-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
