---
title: GetErrorInfo 関数 (アンマネージ API リファレンス)
description: GetErrorInfo 関数は、前の関数呼び出しからエラー情報を取得します。
ms.date: 11/06/2017
api_name:
- GetErrorInfo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetErrorInfo
helpviewer_keywords:
- GetErrorInfo function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 062dc62dfe53af3bf5158cb1add0897eccc1df60
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102615"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="1bbff-103">GetErrorInfo 関数</span><span class="sxs-lookup"><span data-stu-id="1bbff-103">GetErrorInfo function</span></span>
<span data-ttu-id="1bbff-104">前の関数呼び出しからエラー情報が取得されます。</span><span class="sxs-lookup"><span data-stu-id="1bbff-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="1bbff-105">構文</span><span class="sxs-lookup"><span data-stu-id="1bbff-105">Syntax</span></span>  
  
```cpp  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a><span data-ttu-id="1bbff-106">戻り値</span><span class="sxs-lookup"><span data-stu-id="1bbff-106">Return value</span></span>

<span data-ttu-id="1bbff-107">関数呼び出しが成功した場合は[IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo)オブジェクトへのポインター、失敗した場合は `null`。</span><span class="sxs-lookup"><span data-stu-id="1bbff-107">An pointer to an [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="1bbff-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="1bbff-108">Remarks</span></span>

<span data-ttu-id="1bbff-109">この関数は、 [IComThreadingInfo:: GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="1bbff-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="1bbff-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="1bbff-110">Requirements</span></span>  
 <span data-ttu-id="1bbff-111">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bbff-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bbff-112">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="1bbff-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="1bbff-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1bbff-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bbff-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bbff-114">See also</span></span>

- [<span data-ttu-id="1bbff-115">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="1bbff-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
