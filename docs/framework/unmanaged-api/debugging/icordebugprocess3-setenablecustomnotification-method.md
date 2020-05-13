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
ms.openlocfilehash: 523d9665ffd2637a0e856d74d4d3b3838cb5e83c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212127"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="43e98-102">ICorDebugProcess3::SetEnableCustomNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="43e98-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="43e98-103">指定された型のカスタムデバッガー通知を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="43e98-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43e98-104">構文</span><span class="sxs-lookup"><span data-stu-id="43e98-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43e98-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="43e98-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="43e98-106">からカスタムデバッガー通知を指定する型。</span><span class="sxs-lookup"><span data-stu-id="43e98-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="43e98-107">[入力] `true`カスタムデバッガー通知を有効にするには`false`通知を無効にするには</span><span class="sxs-lookup"><span data-stu-id="43e98-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="43e98-108">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="43e98-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43e98-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="43e98-109">Remarks</span></span>  
 <span data-ttu-id="43e98-110">`fEnable`がに設定されている場合 `true` 、メソッドの呼び出しに <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> よって[ICorDebugManagedCallback3:: customnotification](icordebugmanagedcallback3-customnotification-method.md)コールバックがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="43e98-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="43e98-111">既定では、通知は無効になっています。そのため、デバッガーは、認識している通知の種類を指定し、処理を希望する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43e98-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="43e98-112">このクラス[のクラスはアプリケーション](icordebug-interface.md)ドメインによってスコープが設定されているため、 `SetEnableCustomNotification` プロセス全体で通知を受け取る場合は、プロセス内のすべてのアプリケーションドメインに対してを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="43e98-112">Because the [ICorDebugClass](icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="43e98-113">.NET Framework 4 以降、サポートされている通知は、スレッド間の依存関係通知だけです。</span><span class="sxs-lookup"><span data-stu-id="43e98-113">Starting with the .NET Framework 4, the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43e98-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="43e98-114">Requirements</span></span>  
 <span data-ttu-id="43e98-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43e98-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43e98-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43e98-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43e98-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43e98-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43e98-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43e98-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43e98-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="43e98-119">See also</span></span>

- [<span data-ttu-id="43e98-120">ICorDebugProcess3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="43e98-120">ICorDebugProcess3 Interface</span></span>](icordebugprocess3-interface.md)
- [<span data-ttu-id="43e98-121">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="43e98-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="43e98-122">デバッグ</span><span class="sxs-lookup"><span data-stu-id="43e98-122">Debugging</span></span>](index.md)
