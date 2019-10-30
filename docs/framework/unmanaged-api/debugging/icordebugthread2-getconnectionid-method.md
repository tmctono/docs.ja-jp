---
title: ICorDebugThread2::GetConnectionID メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetConnectionID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetConnectionID
helpviewer_keywords:
- ICorDebugThread2::GetConnectionID method [.NET Framework debugging]
- GetConnectionID method [.NET Framework debugging]
ms.assetid: 9c76b587-f941-4fa1-8b86-f3494fb10c8e
topic_type:
- apiref
ms.openlocfilehash: a81842132769934a6f5f34e6dc462bba77b3854a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138685"
---
# <a name="icordebugthread2getconnectionid-method"></a><span data-ttu-id="e9d07-102">ICorDebugThread2::GetConnectionID メソッド</span><span class="sxs-lookup"><span data-stu-id="e9d07-102">ICorDebugThread2::GetConnectionID Method</span></span>
<span data-ttu-id="e9d07-103">この ICorDebugThread2 オブジェクトの接続識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="e9d07-103">Gets the connection identifier for this ICorDebugThread2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9d07-104">構文</span><span class="sxs-lookup"><span data-stu-id="e9d07-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9d07-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e9d07-105">Parameters</span></span>  
 `pdwConnectionId`  
 <span data-ttu-id="e9d07-106">入出力接続識別子を表す `CONNID`。</span><span class="sxs-lookup"><span data-stu-id="e9d07-106">[out] A `CONNID` that represents the connection identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9d07-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e9d07-107">Remarks</span></span>  
 <span data-ttu-id="e9d07-108">このスレッドが接続の一部でない場合、`GetConnectionID` メソッドは、`pdwConnectionId` パラメーターで0を返します。</span><span class="sxs-lookup"><span data-stu-id="e9d07-108">The `GetConnectionID` method returns zero in the `pdwConnectionId` parameter, if this thread is not part of a connection.</span></span>  
  
 <span data-ttu-id="e9d07-109">このスレッドが Microsoft SQL Server 2005 Analysis Services (SSAS) のインスタンスに接続されている場合、`CONNID` はサーバープロセス識別子 (SPID) にマップされます。</span><span class="sxs-lookup"><span data-stu-id="e9d07-109">If this thread is connected to an instance of Microsoft SQL Server 2005 Analysis Services (SSAS), the `CONNID` maps to a server process identifier (SPID).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9d07-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="e9d07-110">Requirements</span></span>  
 <span data-ttu-id="e9d07-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9d07-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9d07-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9d07-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9d07-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9d07-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9d07-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9d07-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
