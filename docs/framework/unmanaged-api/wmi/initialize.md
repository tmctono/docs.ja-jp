---
title: Initialize 関数 (アンマネージ API リファレンス)
description: 初期化関数は、WMI の初期化を実行します。
ms.date: 11/06/2017
api_name:
- Initialize
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Initialize
helpviewer_keywords:
- Initialize function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca8e87157a7adf45f35608aeba1067f2d66c8972
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081607"
---
# <a name="initialize-function"></a><span data-ttu-id="0c155-103">Initialize 関数</span><span class="sxs-lookup"><span data-stu-id="0c155-103">Initialize function</span></span>
<span data-ttu-id="0c155-104">WMI の初期化が実行されます。</span><span class="sxs-lookup"><span data-stu-id="0c155-104">Performs WMI initialization.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="0c155-105">構文</span><span class="sxs-lookup"><span data-stu-id="0c155-105">Syntax</span></span> 
```  
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
); 
```  
## <a name="parameters"></a><span data-ttu-id="0c155-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0c155-106">Parameters</span></span>

`bAllowIManagementObjectQI`   
<span data-ttu-id="0c155-107">[in]`true` WMI オブジェクトの queryinterface 呼び出しが許可されることを示す`false`それ以外の場合。</span><span class="sxs-lookup"><span data-stu-id="0c155-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="0c155-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="0c155-108">Return value</span></span>

<span data-ttu-id="0c155-109">関数は常に返します`S_OK`(0)。</span><span class="sxs-lookup"><span data-stu-id="0c155-109">The function always returns `S_OK` (0).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="0c155-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="0c155-110">Requirements</span></span>  
 <span data-ttu-id="0c155-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c155-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c155-112">**ヘッダー:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="0c155-112">**Header:** WMINet_Utils.def</span></span>  
  
 **<span data-ttu-id="0c155-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="0c155-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0c155-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c155-114">See also</span></span>

- [<span data-ttu-id="0c155-115">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="0c155-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
