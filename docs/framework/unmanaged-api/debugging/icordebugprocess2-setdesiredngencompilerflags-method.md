---
title: ICorDebugProcess2::SetDesiredNGENCompilerFlags メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type:
- apiref
ms.openlocfilehash: 9f62d94d30c8c4f23073895b8ff0f7afa2dbad6b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792494"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a><span data-ttu-id="842ed-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="842ed-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="842ed-103">ランタイムがそのイメージを現在のプロセスに読み込むために、プリコンパイル済みイメージに埋め込む必要があるフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="842ed-103">Sets the flags that must be embedded in a precompiled image in order for the runtime to load that image into the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="842ed-104">構文</span><span class="sxs-lookup"><span data-stu-id="842ed-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="842ed-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="842ed-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="842ed-106">から適切なプリコンパイル済みイメージを選択するために使用されるコンパイラフラグを指定する[CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="842ed-106">[in] A value of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration that specifies the compiler flags used to select the correct pre-compiled image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="842ed-107">コメント</span><span class="sxs-lookup"><span data-stu-id="842ed-107">Remarks</span></span>  
 <span data-ttu-id="842ed-108">`SetDesiredNGENCompilerFlags` メソッドは、プリコンパイル済みイメージに埋め込む必要があるフラグを指定します。これにより、ランタイムはそのイメージをこのプロセスに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="842ed-108">The `SetDesiredNGENCompilerFlags` method specifies the flags that must be embedded in a precompiled image so that the runtime will load that image into this process.</span></span> <span data-ttu-id="842ed-109">このメソッドによって設定されるフラグは、正しいプリコンパイル済みイメージを選択するためにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="842ed-109">The flags set by this method are used only to select the correct precompiled image.</span></span> <span data-ttu-id="842ed-110">そのようなイメージが存在しない場合、ランタイムは Microsoft 中間言語 (MSIL) イメージと just-in-time (JIT) コンパイラを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="842ed-110">If no such image exists, the runtime will load the Microsoft intermediate language (MSIL) image and the just-in-time (JIT) compiler instead.</span></span> <span data-ttu-id="842ed-111">その場合でも、デバッガーは[ICorDebugModule2:: SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md)メソッドを使用して、JIT コンパイルに必要なフラグを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="842ed-111">In that case, the debugger must still use the [ICorDebugModule2::SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md) method to set the flags as desired for the JIT compilation.</span></span>  
  
 <span data-ttu-id="842ed-112">イメージが読み込まれるときに、そのイメージに対して一部の JIT コンパイルを実行する必要がある場合 (イメージにジェネリックが含まれている場合)、`SetDesiredNGENCompilerFlags` メソッドによって指定されたコンパイラフラグが追加の JIT コンパイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="842ed-112">If an image is loaded, but some JIT compiling must take place for that image (which will be the case if the image contains generics), the compiler flags specified by the `SetDesiredNGENCompilerFlags` method will apply to the extra JIT compilation.</span></span>  
  
 <span data-ttu-id="842ed-113">`SetDesiredNGENCompilerFlags` メソッドは、 ["、"](icordebugmanagedcallback-createprocess-method.md)というメソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="842ed-113">The `SetDesiredNGENCompilerFlags` method must be called during the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="842ed-114">その後、`SetDesiredNGENCompilerFlags` メソッドを呼び出そうとすると失敗します。</span><span class="sxs-lookup"><span data-stu-id="842ed-114">Attempts to call the `SetDesiredNGENCompilerFlags` method afterwards will fail.</span></span> <span data-ttu-id="842ed-115">また、`CorDebugJITCompilerFlags` 列挙で定義されていないフラグや、指定されたプロセスに対して有効ではないフラグを設定しようとすると失敗します。</span><span class="sxs-lookup"><span data-stu-id="842ed-115">Also, attempts to set flags that are either not defined in the `CorDebugJITCompilerFlags` enumeration or are not legal for the given process will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="842ed-116">要件</span><span class="sxs-lookup"><span data-stu-id="842ed-116">Requirements</span></span>  
 <span data-ttu-id="842ed-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="842ed-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="842ed-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="842ed-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="842ed-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="842ed-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="842ed-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="842ed-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="842ed-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="842ed-121">See also</span></span>

- [<span data-ttu-id="842ed-122">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="842ed-122">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="842ed-123">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="842ed-123">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
