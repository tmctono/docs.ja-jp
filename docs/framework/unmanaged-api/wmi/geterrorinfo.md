---
title: 関数を取得します (アンマネージ API リファレンス)
description: 関数は、前の関数呼び出しからエラー情報を取得します。
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
ms.openlocfilehash: 802ee66a5be213ac7a599b193ec6de589773ea17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176813"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="ee861-103">GetErrorInfo 関数</span><span class="sxs-lookup"><span data-stu-id="ee861-103">GetErrorInfo function</span></span>
<span data-ttu-id="ee861-104">前の関数呼び出しからエラー情報が取得されます。</span><span class="sxs-lookup"><span data-stu-id="ee861-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ee861-105">構文</span><span class="sxs-lookup"><span data-stu-id="ee861-105">Syntax</span></span>  
  
```cpp  
IErrorInfo* GetErrorInfo();
```  

## <a name="return-value"></a><span data-ttu-id="ee861-106">戻り値</span><span class="sxs-lookup"><span data-stu-id="ee861-106">Return value</span></span>

<span data-ttu-id="ee861-107">関数呼び出しが成功した場合、または`null`失敗した場合は[、IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ee861-107">An pointer to an [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ee861-108">解説</span><span class="sxs-lookup"><span data-stu-id="ee861-108">Remarks</span></span>

<span data-ttu-id="ee861-109">この関数は、メソッドの呼び出し[を](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype)ラップします。</span><span class="sxs-lookup"><span data-stu-id="ee861-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ee861-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="ee861-110">Requirements</span></span>  
 <span data-ttu-id="ee861-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee861-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee861-112">**ヘッダー:** WMINet_Utilsデフ</span><span class="sxs-lookup"><span data-stu-id="ee861-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="ee861-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ee861-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee861-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee861-114">See also</span></span>

- [<span data-ttu-id="ee861-115">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="ee861-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
