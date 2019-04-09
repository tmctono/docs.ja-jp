---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod メソッド
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5cddf34f1a6277e966901c9692bff63e26a3b8e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136735"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="852b4-102">ISymUnmanagedAsyncMethod::IsAsyncMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="852b4-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="852b4-103">かどうかのかどうか、メソッドは非同期の情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="852b4-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="852b4-104">このメソッドが戻る場合`FALSE`し、このインターフェイスで、他のメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="852b4-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="852b4-105">すべての戻り値は`E_UNEXPECTED`ここでします。</span><span class="sxs-lookup"><span data-stu-id="852b4-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="852b4-106">構文</span><span class="sxs-lookup"><span data-stu-id="852b4-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="852b4-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="852b4-107">Parameters</span></span>  
  
|<span data-ttu-id="852b4-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="852b4-108">Parameter</span></span>|<span data-ttu-id="852b4-109">説明</span><span class="sxs-lookup"><span data-stu-id="852b4-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="852b4-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="852b4-110">Return Value</span></span>  
 <span data-ttu-id="852b4-111">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="852b4-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="852b4-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="852b4-112">Requirements</span></span>  
 <span data-ttu-id="852b4-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="852b4-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="852b4-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="852b4-114">See also</span></span>

- [<span data-ttu-id="852b4-115">ISymUnmanagedAsyncMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="852b4-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
