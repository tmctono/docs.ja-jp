---
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount メソッド
ms.date: 03/30/2017
ms.assetid: 32a4e084-09b2-4946-a4a7-19a1fed9f7cc
ms.openlocfilehash: e73f332204f761ff7d72fa14270a5afde985384b
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441865"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfocount-method"></a><span data-ttu-id="9055c-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount メソッド</span><span class="sxs-lookup"><span data-stu-id="9055c-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount Method</span></span>
<span data-ttu-id="9055c-103">「 [DefineAsyncStepInfo メソッド](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9055c-103">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9055c-104">構文</span><span class="sxs-lookup"><span data-stu-id="9055c-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfoCount(    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9055c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9055c-105">Parameters</span></span>  
  
|<span data-ttu-id="9055c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9055c-106">Parameter</span></span>|<span data-ttu-id="9055c-107">説明</span><span class="sxs-lookup"><span data-stu-id="9055c-107">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="9055c-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="9055c-108">Return Value</span></span>  
 <span data-ttu-id="9055c-109">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="9055c-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9055c-110">要件</span><span class="sxs-lookup"><span data-stu-id="9055c-110">Requirements</span></span>  
 <span data-ttu-id="9055c-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="9055c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9055c-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="9055c-112">See also</span></span>

- [<span data-ttu-id="9055c-113">ISymUnmanagedAsyncMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9055c-113">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
