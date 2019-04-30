---
title: ICorPublish::EnumProcesses メソッド
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb4096b0ae083e0b6c0598ea18cc8b33c2fdfe3e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993604"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="cf3c6-102">ICorPublish::EnumProcesses メソッド</span><span class="sxs-lookup"><span data-stu-id="cf3c6-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="cf3c6-103">このコンピューターで実行されている管理対象プロセスの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="cf3c6-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf3c6-104">構文</span><span class="sxs-lookup"><span data-stu-id="cf3c6-104">Syntax</span></span>  
  
```  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf3c6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cf3c6-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="cf3c6-106">値、 [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md)列挙型を取得するプロセスの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="cf3c6-106">A value of the [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="cf3c6-107">現在のバージョンでのみ COR_PUB_MANAGEDONLY は有効です。</span><span class="sxs-lookup"><span data-stu-id="cf3c6-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="cf3c6-108">アドレスへのポインター、 [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)プロセスの列挙子であるインスタンス。</span><span class="sxs-lookup"><span data-stu-id="cf3c6-108">A pointer to the address of an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf3c6-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="cf3c6-109">Remarks</span></span>  
 <span data-ttu-id="cf3c6-110">プロセスの列挙子のコレクションがときに実行しているプロセスのスナップショットに基づいた、`EnumProcesses`メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cf3c6-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="cf3c6-111">列挙子が終了する前に、または後に起動するプロセスは含まれません`EnumProcesses`が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cf3c6-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="cf3c6-112">`EnumProcesses`このメソッドを複数回呼び出すことが[ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)プロセスの新しい最新の状態のコレクションを作成するインスタンス。</span><span class="sxs-lookup"><span data-stu-id="cf3c6-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="cf3c6-113">後続の呼び出しの既存のコレクションを受けませんが、`EnumProcesses`メソッド。</span><span class="sxs-lookup"><span data-stu-id="cf3c6-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf3c6-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="cf3c6-114">Requirements</span></span>  
 <span data-ttu-id="cf3c6-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf3c6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf3c6-116">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="cf3c6-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="cf3c6-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf3c6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf3c6-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf3c6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf3c6-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf3c6-119">See also</span></span>

- [<span data-ttu-id="cf3c6-120">ICorPublish インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cf3c6-120">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
