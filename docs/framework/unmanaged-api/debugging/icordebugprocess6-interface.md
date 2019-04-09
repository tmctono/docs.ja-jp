---
title: ICorDebugProcess6 インターフェイス
ms.date: 03/30/2017
ms.assetid: 34a10ac2-882c-4797-8369-f120e8e640c7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 518c6ec99e4062bf8432809d3472baa395017da3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147265"
---
# <a name="icordebugprocess6-interface"></a><span data-ttu-id="d8a21-102">ICorDebugProcess6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d8a21-102">ICorDebugProcess6 Interface</span></span>
<span data-ttu-id="d8a21-103">ネイティブ例外デバッグ イベントや仮想モジュール分割でエンコードされたマネージ デバッグ イベントをデコードなどの機能を有効にする ICorDebugProcess インターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="d8a21-103">Logically extends the ICorDebugProcess interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d8a21-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="d8a21-104">Methods</span></span>  
  
|<span data-ttu-id="d8a21-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d8a21-105">Method</span></span>|<span data-ttu-id="d8a21-106">説明</span><span class="sxs-lookup"><span data-stu-id="d8a21-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d8a21-107">DecodeEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="d8a21-107">DecodeEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)|<span data-ttu-id="d8a21-108">特別に作成されたネイティブ例外デバッグ イベントのペイロードにカプセル化されたマネージド デバッグ イベントをデコードします。</span><span class="sxs-lookup"><span data-stu-id="d8a21-108">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>|  
|[<span data-ttu-id="d8a21-109">EnableVirtualModuleSplitting メソッド</span><span class="sxs-lookup"><span data-stu-id="d8a21-109">EnableVirtualModuleSplitting Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md)|<span data-ttu-id="d8a21-110">仮想モジュール分割を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="d8a21-110">Enables or disables virtual module splitting.</span></span>|  
|[<span data-ttu-id="d8a21-111">GetCode メソッド</span><span class="sxs-lookup"><span data-stu-id="d8a21-111">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getcode-method.md)|<span data-ttu-id="d8a21-112">特定のコード アドレスで、マネージド コードに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="d8a21-112">Gets information about the managed code at a particular code address.</span></span>|  
|[<span data-ttu-id="d8a21-113">GetExportStepInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="d8a21-113">GetExportStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md)|<span data-ttu-id="d8a21-114">マネージド コードのステップ実行に役立つランタイム エクスポート関数の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d8a21-114">Provides information on runtime exported functions to help step through managed code.</span></span>|  
|[<span data-ttu-id="d8a21-115">MarkDebuggerAttached メソッド</span><span class="sxs-lookup"><span data-stu-id="d8a21-115">MarkDebuggerAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-markdebuggerattached-method.md)|<span data-ttu-id="d8a21-116">.NET Framework クラス ライブラリの <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> メソッドが `true` を返すように、デバッグ対象の内部状態を変更します。</span><span class="sxs-lookup"><span data-stu-id="d8a21-116">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>|  
|[<span data-ttu-id="d8a21-117">ProcessStateChanged メソッド</span><span class="sxs-lookup"><span data-stu-id="d8a21-117">ProcessStateChanged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)|<span data-ttu-id="d8a21-118">通知[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)プロセスが実行されています。</span><span class="sxs-lookup"><span data-stu-id="d8a21-118">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8a21-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="d8a21-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8a21-120">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="d8a21-120">The interface is available with .NET Native only.</span></span> <span data-ttu-id="d8a21-121">インターフェイス ポインターを取得するために `QueryInterface` を呼び出そうとすると、.NET ネイティブ外の ICorDebug シナリオに対して `E_NOINTERFACE` が返されます。</span><span class="sxs-lookup"><span data-stu-id="d8a21-121">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8a21-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="d8a21-122">Requirements</span></span>  
 <span data-ttu-id="d8a21-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8a21-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8a21-124">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8a21-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8a21-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8a21-125">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d8a21-126">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="d8a21-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d8a21-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8a21-127">See also</span></span>

- [<span data-ttu-id="d8a21-128">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="d8a21-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d8a21-129">デバッグ</span><span class="sxs-lookup"><span data-stu-id="d8a21-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
