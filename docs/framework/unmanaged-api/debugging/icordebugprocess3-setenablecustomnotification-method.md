---
title: ICorDebugProcess3::SetEnableCustomNotification メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3.SetEnableCustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c98084b179d27e97ecb3bb34525967d41f8ad1cb
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489616"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="d0f5c-102">ICorDebugProcess3::SetEnableCustomNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="d0f5c-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="d0f5c-103">有効にし、指定した型のカスタムのデバッガー通知を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d0f5c-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0f5c-104">構文</span><span class="sxs-lookup"><span data-stu-id="d0f5c-104">Syntax</span></span>  
  
```  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0f5c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d0f5c-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="d0f5c-106">[in]カスタムのデバッガー通知を指定する型。</span><span class="sxs-lookup"><span data-stu-id="d0f5c-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="d0f5c-107">[in]`true`カスタムのデバッガー通知を有効にするには`false`通知を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d0f5c-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="d0f5c-108">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="d0f5c-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0f5c-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="d0f5c-109">Remarks</span></span>  
 <span data-ttu-id="d0f5c-110">ときに`fEnable`に設定されている`true`への呼び出し、 <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> trigger メソッド、 [icordebugmanagedcallback 3::customnotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="d0f5c-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="d0f5c-111">既定では通知が無効になっていますそのため、デバッガーは、通知の種類が認識し、処理する必要があるを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0f5c-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="d0f5c-112">[ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)クラスのスコープは、アプリケーション ドメインによって、デバッガーを呼び出す必要があります`SetEnableCustomNotification`のプロセス全体で、通知を受信する場合にプロセス内の各アプリケーション ドメイン。</span><span class="sxs-lookup"><span data-stu-id="d0f5c-112">Because the [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="d0f5c-113">以降、.NET Framework 4 では、唯一サポートされている通知は、スレッド間の依存関係の通知です。</span><span class="sxs-lookup"><span data-stu-id="d0f5c-113">Starting with the .NET Framework 4, the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0f5c-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="d0f5c-114">Requirements</span></span>  
 <span data-ttu-id="d0f5c-115">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0f5c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0f5c-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0f5c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0f5c-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0f5c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0f5c-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0f5c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0f5c-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0f5c-119">See also</span></span>

- [<span data-ttu-id="d0f5c-120">ICorDebugProcess3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d0f5c-120">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)
- [<span data-ttu-id="d0f5c-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d0f5c-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d0f5c-122">デバッグ</span><span class="sxs-lookup"><span data-stu-id="d0f5c-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
