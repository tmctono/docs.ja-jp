---
title: 多重化スタブ関数を取得する (アンマネージ API リファレンス)
description: GetDemultiplexedStub関数は、クライアントが Windows 管理から非同期呼び出しを受信するのを支援するオブジェクト フォワーダ シンクを作成します。
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
ms.openlocfilehash: d15fed261db2ca2cda6dbf824dc9cb0d5c56eed3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174967"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="edffb-103">GetDemultiplexedStub 関数</span><span class="sxs-lookup"><span data-stu-id="edffb-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="edffb-104">Windows 管理から非同期呼び出しを受信する際にクライアントを支援するオブジェクト転送シンクが作成されます。</span><span class="sxs-lookup"><span data-stu-id="edffb-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="edffb-105">構文</span><span class="sxs-lookup"><span data-stu-id="edffb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject,
   [in] boolean      isLocal,
   [out] IUnknown**  ppObject
);
```  

## <a name="parameters"></a><span data-ttu-id="edffb-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="edffb-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="edffb-107">[in]クライアントのインプロセス実装の[IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink)へのポインター。</span><span class="sxs-lookup"><span data-stu-id="edffb-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="edffb-108">[in]イベントがローカルかどうかを示すフラグ (`true`;それ以外`false`の場合は、 .</span><span class="sxs-lookup"><span data-stu-id="edffb-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="edffb-109">[アウト]クライアントが Windows 管理から非同期呼び出しを受信するのを支援するオブジェクト フォワーダ シンク。</span><span class="sxs-lookup"><span data-stu-id="edffb-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="edffb-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="edffb-110">Return value</span></span>

<span data-ttu-id="edffb-111">関数が成功した場合、戻り値は`S_OK`(0) になります。</span><span class="sxs-lookup"><span data-stu-id="edffb-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="edffb-112">関数が失敗した場合、戻り値は 0 以外のエラー コードです。</span><span class="sxs-lookup"><span data-stu-id="edffb-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="edffb-113">拡張エラー情報を取得するには[、GetErrorInfo](geterrorinfo.md)関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="edffb-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="edffb-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="edffb-114">Requirements</span></span>  
 <span data-ttu-id="edffb-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edffb-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edffb-116">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="edffb-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="edffb-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="edffb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edffb-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="edffb-118">See also</span></span>

- [<span data-ttu-id="edffb-119">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="edffb-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
