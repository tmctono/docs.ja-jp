---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod メソッド
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: 91b4c2688dadf12fa4a835a662622267d7831cf8
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441800"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="b484f-102">ISymUnmanagedAsyncMethod::IsAsyncMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="b484f-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="b484f-103">メソッドに非同期情報があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b484f-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="b484f-104">このメソッドがを返す場合 `FALSE` 、このインターフェイス内の他のメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="b484f-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="b484f-105">これらはすべて、 `E_UNEXPECTED` この場合はを返します。</span><span class="sxs-lookup"><span data-stu-id="b484f-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b484f-106">構文</span><span class="sxs-lookup"><span data-stu-id="b484f-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b484f-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b484f-107">Parameters</span></span>  
  
|<span data-ttu-id="b484f-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b484f-108">Parameter</span></span>|<span data-ttu-id="b484f-109">説明</span><span class="sxs-lookup"><span data-stu-id="b484f-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="b484f-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="b484f-110">Return Value</span></span>  
 <span data-ttu-id="b484f-111">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="b484f-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b484f-112">要件</span><span class="sxs-lookup"><span data-stu-id="b484f-112">Requirements</span></span>  
 <span data-ttu-id="b484f-113">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="b484f-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b484f-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b484f-114">See also</span></span>

- [<span data-ttu-id="b484f-115">ISymUnmanagedAsyncMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b484f-115">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
