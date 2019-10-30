---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod メソッド
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: 0ea4c21e9e6a49d7bbbad5e1853598c440cd6410
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129210"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="300d9-102">ISymUnmanagedAsyncMethod::IsAsyncMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="300d9-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="300d9-103">メソッドに非同期情報があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="300d9-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="300d9-104">このメソッドが `FALSE` 返す場合は、このインターフェイスで他のメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="300d9-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="300d9-105">これらはすべて、この場合 `E_UNEXPECTED` を返します。</span><span class="sxs-lookup"><span data-stu-id="300d9-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="300d9-106">構文</span><span class="sxs-lookup"><span data-stu-id="300d9-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="300d9-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="300d9-107">Parameters</span></span>  
  
|<span data-ttu-id="300d9-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="300d9-108">Parameter</span></span>|<span data-ttu-id="300d9-109">説明</span><span class="sxs-lookup"><span data-stu-id="300d9-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="300d9-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="300d9-110">Return Value</span></span>  
 <span data-ttu-id="300d9-111">`HRESULT`を返します。</span><span class="sxs-lookup"><span data-stu-id="300d9-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="300d9-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="300d9-112">Requirements</span></span>  
 <span data-ttu-id="300d9-113">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="300d9-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="300d9-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="300d9-114">See also</span></span>

- [<span data-ttu-id="300d9-115">ISymUnmanagedAsyncMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="300d9-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
