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
ms.openlocfilehash: 5f0dd814ad5adfa1b0dd7199530a3f993634a548
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121799"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="76ed7-102">ICorPublish::EnumProcesses メソッド</span><span class="sxs-lookup"><span data-stu-id="76ed7-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="76ed7-103">このコンピューター上で実行されているマネージプロセスの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="76ed7-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76ed7-104">構文</span><span class="sxs-lookup"><span data-stu-id="76ed7-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76ed7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="76ed7-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="76ed7-106">取得するプロセスの種類を指定する[COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="76ed7-106">A value of the [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="76ed7-107">現在のバージョンでは、COR_PUB_MANAGEDONLY のみが有効です。</span><span class="sxs-lookup"><span data-stu-id="76ed7-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="76ed7-108">プロセスの列挙子である[ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)インスタンスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="76ed7-108">A pointer to the address of an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76ed7-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="76ed7-109">Remarks</span></span>  
 <span data-ttu-id="76ed7-110">列挙子のプロセスのコレクションは、`EnumProcesses` メソッドが呼び出されたときに実行されているプロセスのスナップショットに基づいています。</span><span class="sxs-lookup"><span data-stu-id="76ed7-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="76ed7-111">列挙子には、`EnumProcesses` が呼び出された後に終了または開始されるプロセスは含まれません。</span><span class="sxs-lookup"><span data-stu-id="76ed7-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="76ed7-112">この[ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)インスタンスでは、`EnumProcesses` メソッドを複数回呼び出して、新しい最新のプロセスコレクションを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="76ed7-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="76ed7-113">既存のコレクションは、`EnumProcesses` メソッドの後続の呼び出しの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="76ed7-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76ed7-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="76ed7-114">Requirements</span></span>  
 <span data-ttu-id="76ed7-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76ed7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76ed7-116">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="76ed7-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="76ed7-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76ed7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76ed7-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76ed7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76ed7-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="76ed7-119">See also</span></span>

- [<span data-ttu-id="76ed7-120">ICorPublish インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76ed7-120">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
