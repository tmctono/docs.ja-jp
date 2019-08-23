---
title: ICorDebugProcess6::MarkDebuggerAttached メソッド
ms.date: 03/30/2017
ms.assetid: bf94f090-5265-4112-8e57-5b4e20e070d0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c818b196f3252138f2a9c601b04f1d7a6727bc6b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912741"
---
# <a name="icordebugprocess6markdebuggerattached-method"></a><span data-ttu-id="874dc-102">ICorDebugProcess6::MarkDebuggerAttached メソッド</span><span class="sxs-lookup"><span data-stu-id="874dc-102">ICorDebugProcess6::MarkDebuggerAttached Method</span></span>
<span data-ttu-id="874dc-103">.NET Framework クラス ライブラリの <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> メソッドが `true` を返すように、デバッグ対象の内部状態を変更します。</span><span class="sxs-lookup"><span data-stu-id="874dc-103">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="874dc-104">構文</span><span class="sxs-lookup"><span data-stu-id="874dc-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkDebuggerAttached(  
    BOOL fIsAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="874dc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="874dc-105">Parameters</span></span>  
 `fIsAttached`  
 <span data-ttu-id="874dc-106">`true` メソッドが、デバッガーが接続されていることを示す必要がある場合は、<xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType>。それ以外の場合は、`false`。</span><span class="sxs-lookup"><span data-stu-id="874dc-106">`true` if the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method should indicate that a debugger is attached; `false` otherwise.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="874dc-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="874dc-107">Return Value</span></span>  
 <span data-ttu-id="874dc-108">メソッドは、次の表に記載されている値を返す場合があります。</span><span class="sxs-lookup"><span data-stu-id="874dc-108">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="874dc-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="874dc-109">Return value</span></span>|<span data-ttu-id="874dc-110">説明</span><span class="sxs-lookup"><span data-stu-id="874dc-110">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="874dc-111">デバッグ対象は正常に更新されました。</span><span class="sxs-lookup"><span data-stu-id="874dc-111">The debuggee was successfully updated.</span></span>|  
|`CORDBG_E_MODULE_NOT_LOADED`|<span data-ttu-id="874dc-112"><xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> メソッドを格納するアセンブリが読み込まれていないか、メタデータの欠落などの他のエラーが原因で認識されません。</span><span class="sxs-lookup"><span data-stu-id="874dc-112">The assembly that contains the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method is not loaded, or some other error, such as missing metadata, is preventing it from being recognized.</span></span><br /><br /> <span data-ttu-id="874dc-113">このエラーは一般的なもので、問題ありません。</span><span class="sxs-lookup"><span data-stu-id="874dc-113">This error is common and benign.</span></span> <span data-ttu-id="874dc-114">追加のアセンブリを読み込むときに、再度メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="874dc-114">You should call the method again when additional assemblies load.</span></span>|  
|<span data-ttu-id="874dc-115">その他の失敗した `HRESULT` 値。</span><span class="sxs-lookup"><span data-stu-id="874dc-115">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="874dc-116">可能性が高いその他の値は、不適切に動作するデバッガーまたはコンパイラ コンポーネントを示します。</span><span class="sxs-lookup"><span data-stu-id="874dc-116">Other values likely indicate misbehaving debugger or compiler components.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="874dc-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="874dc-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="874dc-118">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="874dc-118">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="874dc-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="874dc-119">Requirements</span></span>  
 <span data-ttu-id="874dc-120">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="874dc-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="874dc-121">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="874dc-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="874dc-122">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="874dc-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="874dc-123">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="874dc-123">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="874dc-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="874dc-124">See also</span></span>

- [<span data-ttu-id="874dc-125">ICorDebugProcess6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="874dc-125">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="874dc-126">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="874dc-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
