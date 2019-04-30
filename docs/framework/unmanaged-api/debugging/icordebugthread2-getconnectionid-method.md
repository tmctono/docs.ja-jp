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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d51e21eab4ac1edc81b58171e5382ada170a57f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946343"
---
# <a name="icordebugthread2getconnectionid-method"></a><span data-ttu-id="ecbc1-102">ICorDebugThread2::GetConnectionID メソッド</span><span class="sxs-lookup"><span data-stu-id="ecbc1-102">ICorDebugThread2::GetConnectionID Method</span></span>
<span data-ttu-id="ecbc1-103">この ICorDebugThread2 オブジェクトの接続識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="ecbc1-103">Gets the connection identifier for this ICorDebugThread2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecbc1-104">構文</span><span class="sxs-lookup"><span data-stu-id="ecbc1-104">Syntax</span></span>  
  
```  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecbc1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ecbc1-105">Parameters</span></span>  
 `pdwConnectionId`  
 <span data-ttu-id="ecbc1-106">[out]A`CONNID`接続識別子を表します。</span><span class="sxs-lookup"><span data-stu-id="ecbc1-106">[out] A `CONNID` that represents the connection identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecbc1-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="ecbc1-107">Remarks</span></span>  
 <span data-ttu-id="ecbc1-108">`GetConnectionID`にゼロが返される、`pdwConnectionId`パラメーターをこのスレッドの接続の一部でない場合。</span><span class="sxs-lookup"><span data-stu-id="ecbc1-108">The `GetConnectionID` method returns zero in the `pdwConnectionId` parameter, if this thread is not part of a connection.</span></span>  
  
 <span data-ttu-id="ecbc1-109">このスレッドがの Microsoft SQL Server 2005 Analysis Services (SSAS)、インスタンスに接続されている場合、`CONNID`サーバー プロセス識別子 (SPID) にマップされます。</span><span class="sxs-lookup"><span data-stu-id="ecbc1-109">If this thread is connected to an instance of Microsoft SQL Server 2005 Analysis Services (SSAS), the `CONNID` maps to a server process identifier (SPID).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecbc1-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="ecbc1-110">Requirements</span></span>  
 <span data-ttu-id="ecbc1-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecbc1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecbc1-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecbc1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecbc1-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecbc1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecbc1-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecbc1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
