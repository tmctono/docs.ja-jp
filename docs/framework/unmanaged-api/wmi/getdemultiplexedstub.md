---
title: GetDemultiplexedStub 関数 (アンマネージ API リファレンス)
description: GetDemultiplexedStub 関数は、クライアントを Windows の管理から非同期呼び出しの受信を支援するために、オブジェクト転送シンクを作成します。
ms.date: 11/06/2017
api_name:
- GetDemultiplexedStub
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetDemultiplexedStub
helpviewer_keywords:
- GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b519ea4062682a56b5b4e277de22b14799f65d0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783214"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="c0e87-103">GetDemultiplexedStub 関数</span><span class="sxs-lookup"><span data-stu-id="c0e87-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="c0e87-104">Windows 管理から非同期呼び出しを受信する際にクライアントを支援するオブジェクト転送シンクが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c0e87-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="c0e87-105">構文</span><span class="sxs-lookup"><span data-stu-id="c0e87-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a><span data-ttu-id="c0e87-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0e87-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="c0e87-107">[in]クライアントのインプロセス実装へのポインター [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink)します。</span><span class="sxs-lookup"><span data-stu-id="c0e87-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="c0e87-108">[in]イベントがローカルかどうかを示すフラグ (`true`)、それ以外の`false`します。</span><span class="sxs-lookup"><span data-stu-id="c0e87-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="c0e87-109">[out]Windows の管理から非同期呼び出しの受信をクライアントを支援するためにオブジェクトのフォワーダー シンク。</span><span class="sxs-lookup"><span data-stu-id="c0e87-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="c0e87-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="c0e87-110">Return value</span></span>

<span data-ttu-id="c0e87-111">関数が成功した場合、戻り値は`S_OK`(0)。</span><span class="sxs-lookup"><span data-stu-id="c0e87-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="c0e87-112">関数が失敗した場合、戻り値が 0 以外のエラー コードにします。</span><span class="sxs-lookup"><span data-stu-id="c0e87-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="c0e87-113">拡張エラー情報を取得する、 [GetErrorInfo](geterrorinfo.md)関数。</span><span class="sxs-lookup"><span data-stu-id="c0e87-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
    
## <a name="requirements"></a><span data-ttu-id="c0e87-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="c0e87-114">Requirements</span></span>  
 <span data-ttu-id="c0e87-115">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0e87-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0e87-116">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c0e87-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c0e87-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c0e87-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0e87-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0e87-118">See also</span></span>

- [<span data-ttu-id="c0e87-119">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="c0e87-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
