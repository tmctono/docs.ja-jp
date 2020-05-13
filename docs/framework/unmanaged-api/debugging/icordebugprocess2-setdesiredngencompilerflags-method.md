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
ms.openlocfilehash: 366a48e5f6abd92f0c6f796f40bdd263181da4a8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213479"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a><span data-ttu-id="d0892-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="d0892-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="d0892-103">ランタイムがそのイメージを現在のプロセスに読み込むために、プリコンパイル済みイメージに埋め込む必要があるフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="d0892-103">Sets the flags that must be embedded in a precompiled image in order for the runtime to load that image into the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0892-104">構文</span><span class="sxs-lookup"><span data-stu-id="d0892-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0892-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d0892-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="d0892-106">から適切なプリコンパイル済みイメージを選択するために使用されるコンパイラフラグを指定する[CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="d0892-106">[in] A value of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration that specifies the compiler flags used to select the correct pre-compiled image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0892-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="d0892-107">Remarks</span></span>  
 <span data-ttu-id="d0892-108">メソッドは、 `SetDesiredNGENCompilerFlags` プリコンパイル済みイメージに埋め込まれる必要があるフラグを指定します。これにより、ランタイムはそのイメージをこのプロセスに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="d0892-108">The `SetDesiredNGENCompilerFlags` method specifies the flags that must be embedded in a precompiled image so that the runtime will load that image into this process.</span></span> <span data-ttu-id="d0892-109">このメソッドによって設定されるフラグは、正しいプリコンパイル済みイメージを選択するためにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="d0892-109">The flags set by this method are used only to select the correct precompiled image.</span></span> <span data-ttu-id="d0892-110">そのようなイメージが存在しない場合、ランタイムは Microsoft 中間言語 (MSIL) イメージと just-in-time (JIT) コンパイラを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="d0892-110">If no such image exists, the runtime will load the Microsoft intermediate language (MSIL) image and the just-in-time (JIT) compiler instead.</span></span> <span data-ttu-id="d0892-111">その場合でも、デバッガーは[ICorDebugModule2:: SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md)メソッドを使用して、JIT コンパイルに必要なフラグを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0892-111">In that case, the debugger must still use the [ICorDebugModule2::SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md) method to set the flags as desired for the JIT compilation.</span></span>  
  
 <span data-ttu-id="d0892-112">イメージが読み込まれるときに、そのイメージに対して一部の JIT コンパイルを実行する必要がある場合 (イメージにジェネリックが含まれている場合)、メソッドによって指定されたコンパイラフラグ `SetDesiredNGENCompilerFlags` が追加の jit コンパイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d0892-112">If an image is loaded, but some JIT compiling must take place for that image (which will be the case if the image contains generics), the compiler flags specified by the `SetDesiredNGENCompilerFlags` method will apply to the extra JIT compilation.</span></span>  
  
 <span data-ttu-id="d0892-113">このメソッドは、の `SetDesiredNGENCompilerFlags` メソッドを[ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md)呼び出さなければなりません。</span><span class="sxs-lookup"><span data-stu-id="d0892-113">The `SetDesiredNGENCompilerFlags` method must be called during the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="d0892-114">その後、メソッドを呼び出そうとすると `SetDesiredNGENCompilerFlags` 失敗します。</span><span class="sxs-lookup"><span data-stu-id="d0892-114">Attempts to call the `SetDesiredNGENCompilerFlags` method afterwards will fail.</span></span> <span data-ttu-id="d0892-115">また、列挙型で定義されていないフラグや、指定されたプロセスに対して有効ではないフラグを設定しようとすると `CorDebugJITCompilerFlags` 失敗します。</span><span class="sxs-lookup"><span data-stu-id="d0892-115">Also, attempts to set flags that are either not defined in the `CorDebugJITCompilerFlags` enumeration or are not legal for the given process will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0892-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="d0892-116">Requirements</span></span>  
 <span data-ttu-id="d0892-117">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0892-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0892-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0892-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0892-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0892-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0892-120">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0892-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0892-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0892-121">See also</span></span>

- [<span data-ttu-id="d0892-122">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d0892-122">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="d0892-123">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d0892-123">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
