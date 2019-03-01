---
title: ICorDebugAppDomain インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain
helpviewer_keywords:
- ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db2052bafb259f07370f007f699f6858c532b11d
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973757"
---
# <a name="icordebugappdomain-interface"></a><span data-ttu-id="6a4f9-102">ICorDebugAppDomain インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a4f9-102">ICorDebugAppDomain Interface</span></span>

<span data-ttu-id="6a4f9-103">アプリケーション ドメインをデバッグするためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="6a4f9-104">このインターフェイスは、ICorDebugController のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6a4f9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="6a4f9-105">Methods</span></span>  
  
|<span data-ttu-id="6a4f9-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="6a4f9-106">Method</span></span>|<span data-ttu-id="6a4f9-107">説明</span><span class="sxs-lookup"><span data-stu-id="6a4f9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6a4f9-108">Attach メソッド</span><span class="sxs-lookup"><span data-stu-id="6a4f9-108">Attach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|<span data-ttu-id="6a4f9-109">アプリケーション ドメインに、デバッガーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="6a4f9-110">EnumerateAssemblies メソッド</span><span class="sxs-lookup"><span data-stu-id="6a4f9-110">EnumerateAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="6a4f9-111">アプリケーション ドメインでアセンブリの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="6a4f9-112">EnumerateBreakpoints メソッド</span><span class="sxs-lookup"><span data-stu-id="6a4f9-112">EnumerateBreakpoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="6a4f9-113">アプリケーション ドメインですべてのアクティブなブレークポイントの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="6a4f9-114">EnumerateSteppers メソッド</span><span class="sxs-lookup"><span data-stu-id="6a4f9-114">EnumerateSteppers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="6a4f9-115">アプリケーション ドメイン内のすべてのアクティブ ステッパの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="6a4f9-116">GetID メソッド</span><span class="sxs-lookup"><span data-stu-id="6a4f9-116">GetId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|<span data-ttu-id="6a4f9-117">アプリケーション ドメインの一意の ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="6a4f9-118">GetModuleFromMetaDataInterface メソッド</span><span class="sxs-lookup"><span data-stu-id="6a4f9-118">GetModuleFromMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="6a4f9-119">特定のメタデータ インターフェイスを持つ ICorDebugModule オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="6a4f9-120">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="6a4f9-120">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|<span data-ttu-id="6a4f9-121">アプリケーション ドメインの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="6a4f9-122">GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="6a4f9-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|<span data-ttu-id="6a4f9-123">共通言語ランタイム (CLR) のアプリケーション ドメインにインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="6a4f9-124">GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="6a4f9-124">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|<span data-ttu-id="6a4f9-125">アプリケーション ドメインを格納しているプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="6a4f9-126">IsAttached メソッド</span><span class="sxs-lookup"><span data-stu-id="6a4f9-126">IsAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|<span data-ttu-id="6a4f9-127">アプリケーション ドメインに、デバッガーがアタッチされているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a4f9-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="6a4f9-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a4f9-129">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a4f9-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="6a4f9-130">Requirements</span></span>  
 <span data-ttu-id="6a4f9-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a4f9-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a4f9-132">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a4f9-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a4f9-133">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a4f9-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a4f9-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a4f9-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a4f9-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a4f9-135">See also</span></span>
- [<span data-ttu-id="6a4f9-136">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a4f9-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
