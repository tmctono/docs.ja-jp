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
ms.openlocfilehash: 12753ab65f9339e8f6c3049bb72755e87464eb1a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963110"
---
# <a name="icordebugappdomain-interface"></a><span data-ttu-id="a8ffe-102">ICorDebugAppDomain インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a8ffe-102">ICorDebugAppDomain Interface</span></span>

<span data-ttu-id="a8ffe-103">アプリケーション ドメインをデバッグするためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="a8ffe-104">このインターフェイスは、というコントロールのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8ffe-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a8ffe-105">Methods</span></span>  
  
|<span data-ttu-id="a8ffe-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="a8ffe-106">Method</span></span>|<span data-ttu-id="a8ffe-107">説明</span><span class="sxs-lookup"><span data-stu-id="a8ffe-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a8ffe-108">Attach メソッド</span><span class="sxs-lookup"><span data-stu-id="a8ffe-108">Attach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|<span data-ttu-id="a8ffe-109">デバッガーをアプリケーションドメインにアタッチします。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="a8ffe-110">EnumerateAssemblies メソッド</span><span class="sxs-lookup"><span data-stu-id="a8ffe-110">EnumerateAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="a8ffe-111">アプリケーションドメイン内のアセンブリの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="a8ffe-112">EnumerateBreakpoints メソッド</span><span class="sxs-lookup"><span data-stu-id="a8ffe-112">EnumerateBreakpoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="a8ffe-113">アプリケーションドメイン内のすべてのアクティブなブレークポイントの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="a8ffe-114">EnumerateSteppers メソッド</span><span class="sxs-lookup"><span data-stu-id="a8ffe-114">EnumerateSteppers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="a8ffe-115">アプリケーションドメイン内のすべてのアクティブな steppers の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="a8ffe-116">GetID メソッド</span><span class="sxs-lookup"><span data-stu-id="a8ffe-116">GetId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|<span data-ttu-id="a8ffe-117">アプリケーションドメインの一意の ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="a8ffe-118">GetModuleFromMetaDataInterface メソッド</span><span class="sxs-lookup"><span data-stu-id="a8ffe-118">GetModuleFromMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="a8ffe-119">指定されたメタデータインターフェイスを持つ、のモジュールオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="a8ffe-120">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="a8ffe-120">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|<span data-ttu-id="a8ffe-121">アプリケーションドメインの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="a8ffe-122">GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="a8ffe-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|<span data-ttu-id="a8ffe-123">共通言語ランタイム (CLR) アプリケーションドメインへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="a8ffe-124">GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="a8ffe-124">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|<span data-ttu-id="a8ffe-125">アプリケーションドメインを格納しているプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="a8ffe-126">IsAttached メソッド</span><span class="sxs-lookup"><span data-stu-id="a8ffe-126">IsAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|<span data-ttu-id="a8ffe-127">デバッガーがアプリケーションドメインにアタッチされているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8ffe-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="a8ffe-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a8ffe-129">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8ffe-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="a8ffe-130">Requirements</span></span>  
 <span data-ttu-id="a8ffe-131">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8ffe-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8ffe-132">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="a8ffe-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8ffe-133">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="a8ffe-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8ffe-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8ffe-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8ffe-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8ffe-135">See also</span></span>

- [<span data-ttu-id="a8ffe-136">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a8ffe-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
