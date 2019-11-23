---
title: ISymUnmanagedReader::GetMethodVersion メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
ms.openlocfilehash: fcaf748413321f684336543e60f735af69894b51
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436013"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="d8d76-102">ISymUnmanagedReader::GetMethodVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d76-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="d8d76-103">Gets the method version.</span><span class="sxs-lookup"><span data-stu-id="d8d76-103">Gets the method version.</span></span> <span data-ttu-id="d8d76-104">The method version starts at 1 and is incremented each time the method is recompiled.</span><span class="sxs-lookup"><span data-stu-id="d8d76-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="d8d76-105">Recompilation can happen without changes to the method.</span><span class="sxs-lookup"><span data-stu-id="d8d76-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8d76-106">構文</span><span class="sxs-lookup"><span data-stu-id="d8d76-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8d76-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d8d76-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="d8d76-108">[in] The method for which to get the version.</span><span class="sxs-lookup"><span data-stu-id="d8d76-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="d8d76-109">[out] A pointer to a variable that receives the method version.</span><span class="sxs-lookup"><span data-stu-id="d8d76-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8d76-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="d8d76-110">Return Value</span></span>  
 <span data-ttu-id="d8d76-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="d8d76-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8d76-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="d8d76-112">Requirements</span></span>  
 <span data-ttu-id="d8d76-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d8d76-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8d76-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8d76-114">See also</span></span>

- [<span data-ttu-id="d8d76-115">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d8d76-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
