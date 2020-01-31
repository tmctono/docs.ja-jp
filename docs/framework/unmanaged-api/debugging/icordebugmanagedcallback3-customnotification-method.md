---
title: ICorDebugManagedCallback3::CustomNotification メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3.CustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3::CustomNotification
helpviewer_keywords:
- ICorDebugManagedCallback3::CustomNotification method [.NET Framework debugging]
- CustomNotification method [.NET Framework debugging]
ms.assetid: 5e5422ac-afa1-403d-a894-2d7348673e38
topic_type:
- apiref
ms.openlocfilehash: 078f90387a475559067d402610ec264f4076ae01
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793263"
---
# <a name="icordebugmanagedcallback3customnotification-method"></a><span data-ttu-id="37ed4-102">ICorDebugManagedCallback3::CustomNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="37ed4-102">ICorDebugManagedCallback3::CustomNotification Method</span></span>
<span data-ttu-id="37ed4-103">カスタムデバッガー通知が発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="37ed4-103">Indicates that a custom debugger notification has been raised.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37ed4-104">構文</span><span class="sxs-lookup"><span data-stu-id="37ed4-104">Syntax</span></span>  
  
```cpp  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37ed4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="37ed4-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="37ed4-106">から通知を発生させたスレッドへのポインター。</span><span class="sxs-lookup"><span data-stu-id="37ed4-106">[in] A pointer to the thread that raised the notification.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="37ed4-107">から通知を発生させたスレッドを含むアプリケーションドメインへのポインター。</span><span class="sxs-lookup"><span data-stu-id="37ed4-107">[in] A pointer to the application domain that contains the thread that raised the notification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37ed4-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="37ed4-108">Return Value</span></span>  
 <span data-ttu-id="37ed4-109">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="37ed4-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="37ed4-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="37ed4-110">HRESULT</span></span>|<span data-ttu-id="37ed4-111">説明</span><span class="sxs-lookup"><span data-stu-id="37ed4-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="37ed4-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="37ed4-112">S_OK</span></span>|<span data-ttu-id="37ed4-113">メソッドは正常に終了しました。</span><span class="sxs-lookup"><span data-stu-id="37ed4-113">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="37ed4-114">例外</span><span class="sxs-lookup"><span data-stu-id="37ed4-114">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37ed4-115">コメント</span><span class="sxs-lookup"><span data-stu-id="37ed4-115">Remarks</span></span>  
 <span data-ttu-id="37ed4-116">後続の[ICorDebugThread4:: Getcurrentcustomデバッガ通知](icordebugthread4-getcurrentcustomdebuggernotification-method.md)メソッドの呼び出しでは、<xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> メソッドに渡されたスレッドオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="37ed4-116">A subsequent call to the [ICorDebugThread4::GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md) method retrieves the thread object that was passed to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="37ed4-117">スレッドオブジェクトの型は、 [ICorDebugProcess3:: SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md)メソッドを呼び出すことによって既に有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="37ed4-117">The thread object's type must have been previously enabled by calling the [ICorDebugProcess3::SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md) method.</span></span> <span data-ttu-id="37ed4-118">デバッガーは、スレッドオブジェクトのフィールドから型固有のパラメーターを読み取ることができ、応答をフィールドに格納できます。</span><span class="sxs-lookup"><span data-stu-id="37ed4-118">The debugger can read type-specific parameters from the fields of the thread object, and can store responses into fields.</span></span>  
  
 <span data-ttu-id="37ed4-119">[ICorDebug](icordebug-interface.md)インターフェイスでは、通知の種類やその内容にポリシーは適用されません。また、通知のセマンティクスは、厳密にはデバッガー、アプリケーション、および .NET Framework 間のコントラクトになります。</span><span class="sxs-lookup"><span data-stu-id="37ed4-119">The [ICorDebug](icordebug-interface.md) interface imposes no policy on the types of notifications or their contents, and the semantics of the notifications are strictly a contract between debuggers, applications, and the .NET Framework.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37ed4-120">要件</span><span class="sxs-lookup"><span data-stu-id="37ed4-120">Requirements</span></span>  
 <span data-ttu-id="37ed4-121">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37ed4-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37ed4-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="37ed4-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37ed4-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37ed4-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37ed4-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37ed4-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37ed4-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="37ed4-125">See also</span></span>

- [<span data-ttu-id="37ed4-126">ICorDebugManagedCallback3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="37ed4-126">ICorDebugManagedCallback3 Interface</span></span>](icordebugmanagedcallback3-interface.md)
- [<span data-ttu-id="37ed4-127">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="37ed4-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="37ed4-128">デバッグ</span><span class="sxs-lookup"><span data-stu-id="37ed4-128">Debugging</span></span>](index.md)
