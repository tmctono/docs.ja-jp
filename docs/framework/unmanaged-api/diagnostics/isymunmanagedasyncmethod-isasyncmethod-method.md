---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod メソッド
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 460d6781405b6042262d50e1aa79ee8c77f781a7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489723"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="7e2b6-102">ISymUnmanagedAsyncMethod::IsAsyncMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="7e2b6-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="7e2b6-103">かどうかのかどうか、メソッドは非同期の情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="7e2b6-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="7e2b6-104">このメソッドが戻る場合`FALSE`し、このインターフェイスで、他のメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="7e2b6-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="7e2b6-105">すべての戻り値は`E_UNEXPECTED`ここでします。</span><span class="sxs-lookup"><span data-stu-id="7e2b6-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e2b6-106">構文</span><span class="sxs-lookup"><span data-stu-id="7e2b6-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e2b6-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7e2b6-107">Parameters</span></span>  
  
|<span data-ttu-id="7e2b6-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7e2b6-108">Parameter</span></span>|<span data-ttu-id="7e2b6-109">説明</span><span class="sxs-lookup"><span data-stu-id="7e2b6-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="7e2b6-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="7e2b6-110">Return Value</span></span>  
 <span data-ttu-id="7e2b6-111">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="7e2b6-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e2b6-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="7e2b6-112">Requirements</span></span>  
 <span data-ttu-id="7e2b6-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7e2b6-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e2b6-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e2b6-114">See also</span></span>
- [<span data-ttu-id="7e2b6-115">ISymUnmanagedAsyncMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7e2b6-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
