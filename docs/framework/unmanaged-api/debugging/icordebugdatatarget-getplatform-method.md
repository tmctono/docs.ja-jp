---
title: ICorDebugDataTarget::GetPlatform メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetPlatform Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 309c31dacd801f1c46a2d37932124638bc157cd6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214028"
---
# <a name="icordebugdatatargetgetplatform-method"></a><span data-ttu-id="cd4e2-102">ICorDebugDataTarget::GetPlatform メソッド</span><span class="sxs-lookup"><span data-stu-id="cd4e2-102">ICorDebugDataTarget::GetPlatform Method</span></span>
<span data-ttu-id="cd4e2-103">プロセッサ アーキテクチャと、ターゲット プロセスが実行されているオペレーティング システムを含む、プラットフォームについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cd4e2-103">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd4e2-104">構文</span><span class="sxs-lookup"><span data-stu-id="cd4e2-104">Syntax</span></span>  
  
```  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd4e2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cd4e2-105">Parameters</span></span>  
 `pTargetPlatform`  
 <span data-ttu-id="cd4e2-106">[out]ポインターを[CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md)ターゲット プラットフォームを表す列挙体。</span><span class="sxs-lookup"><span data-stu-id="cd4e2-106">[out] A pointer to a [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration that describes the target platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd4e2-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="cd4e2-107">Remarks</span></span>  
 <span data-ttu-id="cd4e2-108">`CorDebugPlatformEnum`列挙型の戻り値を使って、 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)インターフェイス ポインターのサイズ、アドレス空間レイアウト、レジスタ セット、命令の形式、コンテキストのレイアウトなど、ターゲット プロセスの詳細を確認して呼び出し規約。</span><span class="sxs-lookup"><span data-stu-id="cd4e2-108">The `CorDebugPlatformEnum` enumeration return value is used by the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface to determine details of the target process such as its pointer size, address space layout, register set, instruction format, context layout, and calling conventions.</span></span>  
  
 <span data-ttu-id="cd4e2-109">`pTargetPlatform`値可能性がありますが、実際のハードウェアを使用して指定する代わりに、ターゲットのエミュレートされるプラットフォームを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd4e2-109">The `pTargetPlatform` value may refer to a platform that is being emulated for the target instead of specifying the actual hardware in use.</span></span> <span data-ttu-id="cd4e2-110">たとえば、Windows オペレーティング システムの 64 ビット版 Windows (WOW) 環境での Windows で実行されているプロセスを使用する必要があります、`CORDB_PLATFORM_WINDOWS_X86`の値、 [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md)列挙体。</span><span class="sxs-lookup"><span data-stu-id="cd4e2-110">For example, a process that is running in the Windows on Windows (WOW) environment on a 64-bit edition of the Windows operating system should use the `CORDB_PLATFORM_WINDOWS_X86` value of the [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="cd4e2-111">このメソッドは成功する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd4e2-111">This method must succeed.</span></span> <span data-ttu-id="cd4e2-112">失敗した場合、ターゲット プラットフォームは使用できません。</span><span class="sxs-lookup"><span data-stu-id="cd4e2-112">If it fails, the target platform is unusable.</span></span> <span data-ttu-id="cd4e2-113">メソッドは、次の理由で失敗します。</span><span class="sxs-lookup"><span data-stu-id="cd4e2-113">The method may fail for the following reasons:</span></span>  
  
-   <span data-ttu-id="cd4e2-114">ターゲットのエミュレートされているプラットフォームでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="cd4e2-114">The platform that is being emulated for the target is unusable.</span></span>  
  
-   <span data-ttu-id="cd4e2-115">ターゲット プラットフォームの実際のハードウェアが使用できません。</span><span class="sxs-lookup"><span data-stu-id="cd4e2-115">The actual hardware on the target platform is unusable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd4e2-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="cd4e2-116">Requirements</span></span>  
 <span data-ttu-id="cd4e2-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd4e2-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd4e2-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd4e2-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd4e2-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd4e2-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd4e2-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd4e2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd4e2-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd4e2-121">See also</span></span>

- [<span data-ttu-id="cd4e2-122">ICorDebugDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cd4e2-122">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="cd4e2-123">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cd4e2-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="cd4e2-124">デバッグ</span><span class="sxs-lookup"><span data-stu-id="cd4e2-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
