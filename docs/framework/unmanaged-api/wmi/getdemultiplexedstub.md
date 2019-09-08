---
title: GetDemultiplexedStub 関数 (アンマネージ API リファレンス)
description: GetDemultiplexedStub 関数は、Windows Management からの非同期呼び出しをクライアントが受信するのを支援するオブジェクトフォワーダーシンクを作成します。
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
ms.openlocfilehash: a2d3885a4a9e54950909053ba18de5b1891e7edf
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798604"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="73a64-103">GetDemultiplexedStub 関数</span><span class="sxs-lookup"><span data-stu-id="73a64-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="73a64-104">Windows 管理から非同期呼び出しを受信する際にクライアントを支援するオブジェクト転送シンクが作成されます。</span><span class="sxs-lookup"><span data-stu-id="73a64-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="73a64-105">構文</span><span class="sxs-lookup"><span data-stu-id="73a64-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a><span data-ttu-id="73a64-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="73a64-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="73a64-107">から[IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink)のクライアントのインプロセス実装へのポインター。</span><span class="sxs-lookup"><span data-stu-id="73a64-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="73a64-108">からイベントがローカル (`true`) であるかどうかを示すフラグ。それ以外の場合`false`は。</span><span class="sxs-lookup"><span data-stu-id="73a64-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="73a64-109">入出力Windows Management からの非同期呼び出しをクライアントが受信するのを支援するオブジェクトフォワーダーシンク。</span><span class="sxs-lookup"><span data-stu-id="73a64-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="73a64-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="73a64-110">Return value</span></span>

<span data-ttu-id="73a64-111">関数が成功した場合、戻り値`S_OK`は (0) になります。</span><span class="sxs-lookup"><span data-stu-id="73a64-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="73a64-112">関数が失敗した場合、戻り値は0以外のエラーコードです。</span><span class="sxs-lookup"><span data-stu-id="73a64-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="73a64-113">拡張されたエラー情報を取得するには、 [GetErrorInfo](geterrorinfo.md)関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="73a64-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
    
## <a name="requirements"></a><span data-ttu-id="73a64-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="73a64-114">Requirements</span></span>  
 <span data-ttu-id="73a64-115">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="73a64-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73a64-116">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="73a64-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="73a64-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="73a64-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73a64-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="73a64-118">See also</span></span>

- [<span data-ttu-id="73a64-119">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="73a64-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
