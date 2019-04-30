---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod メソッド
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5cddf34f1a6277e966901c9692bff63e26a3b8e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940154"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="d17a2-102">ISymUnmanagedAsyncMethod::IsAsyncMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="d17a2-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="d17a2-103">かどうかのかどうか、メソッドは非同期の情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="d17a2-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="d17a2-104">このメソッドが戻る場合`FALSE`し、このインターフェイスで、他のメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="d17a2-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="d17a2-105">すべての戻り値は`E_UNEXPECTED`ここでします。</span><span class="sxs-lookup"><span data-stu-id="d17a2-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d17a2-106">構文</span><span class="sxs-lookup"><span data-stu-id="d17a2-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d17a2-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d17a2-107">Parameters</span></span>  
  
|<span data-ttu-id="d17a2-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d17a2-108">Parameter</span></span>|<span data-ttu-id="d17a2-109">説明</span><span class="sxs-lookup"><span data-stu-id="d17a2-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="d17a2-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="d17a2-110">Return Value</span></span>  
 <span data-ttu-id="d17a2-111">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="d17a2-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d17a2-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="d17a2-112">Requirements</span></span>  
 <span data-ttu-id="d17a2-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d17a2-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d17a2-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d17a2-114">See also</span></span>

- [<span data-ttu-id="d17a2-115">ISymUnmanagedAsyncMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d17a2-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
