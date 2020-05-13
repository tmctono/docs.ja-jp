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
ms.openlocfilehash: 8a4620e591cc80efb5c0fd53b0edf3a35849c421
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209761"
---
# <a name="icordebugmanagedcallback3customnotification-method"></a><span data-ttu-id="0815f-102">ICorDebugManagedCallback3::CustomNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="0815f-102">ICorDebugManagedCallback3::CustomNotification Method</span></span>
<span data-ttu-id="0815f-103">カスタムデバッガー通知が発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="0815f-103">Indicates that a custom debugger notification has been raised.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0815f-104">構文</span><span class="sxs-lookup"><span data-stu-id="0815f-104">Syntax</span></span>  
  
```cpp  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0815f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0815f-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="0815f-106">から通知を発生させたスレッドへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0815f-106">[in] A pointer to the thread that raised the notification.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="0815f-107">から通知を発生させたスレッドを含むアプリケーションドメインへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0815f-107">[in] A pointer to the application domain that contains the thread that raised the notification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0815f-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="0815f-108">Return Value</span></span>  
 <span data-ttu-id="0815f-109">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="0815f-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0815f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0815f-110">HRESULT</span></span>|<span data-ttu-id="0815f-111">説明</span><span class="sxs-lookup"><span data-stu-id="0815f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0815f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0815f-112">S_OK</span></span>|<span data-ttu-id="0815f-113">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="0815f-113">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="0815f-114">例外</span><span class="sxs-lookup"><span data-stu-id="0815f-114">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0815f-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="0815f-115">Remarks</span></span>  
 <span data-ttu-id="0815f-116">後続の[ICorDebugThread4:: Getcurrentcustomデバッガ通知](icordebugthread4-getcurrentcustomdebuggernotification-method.md)メソッドの呼び出しでは、メソッドに渡されたスレッドオブジェクトを取得し <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="0815f-116">A subsequent call to the [ICorDebugThread4::GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md) method retrieves the thread object that was passed to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="0815f-117">スレッドオブジェクトの型は、 [ICorDebugProcess3:: SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md)メソッドを呼び出すことによって既に有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0815f-117">The thread object's type must have been previously enabled by calling the [ICorDebugProcess3::SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md) method.</span></span> <span data-ttu-id="0815f-118">デバッガーは、スレッドオブジェクトのフィールドから型固有のパラメーターを読み取ることができ、応答をフィールドに格納できます。</span><span class="sxs-lookup"><span data-stu-id="0815f-118">The debugger can read type-specific parameters from the fields of the thread object, and can store responses into fields.</span></span>  
  
 <span data-ttu-id="0815f-119">[ICorDebug](icordebug-interface.md)インターフェイスでは、通知の種類やその内容にポリシーは適用されません。また、通知のセマンティクスは、厳密にはデバッガー、アプリケーション、および .NET Framework 間のコントラクトになります。</span><span class="sxs-lookup"><span data-stu-id="0815f-119">The [ICorDebug](icordebug-interface.md) interface imposes no policy on the types of notifications or their contents, and the semantics of the notifications are strictly a contract between debuggers, applications, and the .NET Framework.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0815f-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="0815f-120">Requirements</span></span>  
 <span data-ttu-id="0815f-121">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0815f-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0815f-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0815f-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0815f-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0815f-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0815f-124">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0815f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0815f-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="0815f-125">See also</span></span>

- [<span data-ttu-id="0815f-126">ICorDebugManagedCallback3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0815f-126">ICorDebugManagedCallback3 Interface</span></span>](icordebugmanagedcallback3-interface.md)
- [<span data-ttu-id="0815f-127">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="0815f-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0815f-128">デバッグ</span><span class="sxs-lookup"><span data-stu-id="0815f-128">Debugging</span></span>](index.md)
