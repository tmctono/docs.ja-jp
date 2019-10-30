---
title: ICorDebugModule2::ApplyChanges メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ApplyChanges
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ApplyChanges
helpviewer_keywords:
- ApplyChanges method [.NET Framework debugging]
- ICorDebugModule2::ApplyChanges method [.NET Framework debugging]
ms.assetid: 96fa3406-6a6f-41a1-88c6-d9bc5d1a16d1
topic_type:
- apiref
ms.openlocfilehash: c324019e1e62701f4f2aaba1c00948b292ba6847
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127912"
---
# <a name="icordebugmodule2applychanges-method"></a><span data-ttu-id="bc94c-102">ICorDebugModule2::ApplyChanges メソッド</span><span class="sxs-lookup"><span data-stu-id="bc94c-102">ICorDebugModule2::ApplyChanges Method</span></span>
<span data-ttu-id="bc94c-103">メタデータの変更と、Microsoft 中間言語 (MSIL) コードの変更を実行中のプロセスに適用します。</span><span class="sxs-lookup"><span data-stu-id="bc94c-103">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc94c-104">構文</span><span class="sxs-lookup"><span data-stu-id="bc94c-104">Syntax</span></span>  
  
```cpp  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc94c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bc94c-105">Parameters</span></span>  
 `cbMetadata`  
 <span data-ttu-id="bc94c-106">からデルタメタデータのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="bc94c-106">[in] Size, in bytes, of the delta metadata.</span></span>  
  
 `pbMetadata`  
 <span data-ttu-id="bc94c-107">からデルタメタデータを格納しているバッファー。</span><span class="sxs-lookup"><span data-stu-id="bc94c-107">[in] Buffer that contains the delta metadata.</span></span> <span data-ttu-id="bc94c-108">バッファーのアドレスは、 [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)メソッドから返されます。</span><span class="sxs-lookup"><span data-stu-id="bc94c-108">The address of the buffer is returned from the [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) method.</span></span>  
  
 <span data-ttu-id="bc94c-109">メタデータ内の相対仮想アドレス (RVAs) は、MSIL コードの先頭に対して相対的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc94c-109">The relative virtual addresses (RVAs) in the metadata should be relative to the start of the MSIL code.</span></span>  
  
 `cbIL`  
 <span data-ttu-id="bc94c-110">からデルタ MSIL コードのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="bc94c-110">[in] Size, in bytes, of the delta MSIL code.</span></span>  
  
 `pbIL`  
 <span data-ttu-id="bc94c-111">から更新された MSIL コードを格納しているバッファー。</span><span class="sxs-lookup"><span data-stu-id="bc94c-111">[in] Buffer that contains the updated MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc94c-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="bc94c-112">Remarks</span></span>  
 <span data-ttu-id="bc94c-113">`pbMetadata` パラメーターは、( [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)によって出力される) 特別なデルタメタデータ形式です。</span><span class="sxs-lookup"><span data-stu-id="bc94c-113">The `pbMetadata` parameter is in a special delta metadata format (as output by [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)).</span></span> <span data-ttu-id="bc94c-114">`pbMetadata` は、前のメタデータをベースとして受け取り、そのベースに適用する個々の変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc94c-114">`pbMetadata` takes previous metadata as a base and describes individual changes to apply to that base.</span></span>  
  
 <span data-ttu-id="bc94c-115">これに対して、`pbIL[`] パラメーターには、更新されたメソッドの新しい MSIL が含まれます。これは、そのメソッドの前の MSIL を完全に置き換えることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="bc94c-115">In contrast, the `pbIL[`] parameter contains the new MSIL for the updated method, and is meant to completely replace the previous MSIL for that method</span></span>  
  
 <span data-ttu-id="bc94c-116">デルタ MSIL とメタデータがデバッガーのメモリ内に作成されると、デバッガーは `ApplyChanges` を呼び出して、変更を共通言語ランタイム (CLR) に送信します。</span><span class="sxs-lookup"><span data-stu-id="bc94c-116">When the delta MSIL and the metadata have been created in the debugger’s memory, the debugger calls `ApplyChanges` to send the changes into the common language runtime (CLR).</span></span> <span data-ttu-id="bc94c-117">ランタイムはそのメタデータテーブルを更新し、新しい MSIL をプロセスに配置して、新しい MSIL の just-in-time (JIT) コンパイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="bc94c-117">The runtime updates its metadata tables, places the new MSIL into the process, and sets up a just-in-time (JIT) compilation of the new MSIL.</span></span> <span data-ttu-id="bc94c-118">変更が適用されると、デバッガーは[IMetaDataEmit2:: ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)を呼び出して、次の編集セッションの準備を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc94c-118">When the changes have been applied, the debugger should call [IMetaDataEmit2::ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) to prepare for the next editing session.</span></span> <span data-ttu-id="bc94c-119">デバッガーはプロセスを続行できます。</span><span class="sxs-lookup"><span data-stu-id="bc94c-119">The debugger may then continue the process.</span></span>  
  
 <span data-ttu-id="bc94c-120">デバッガーは、デルタメタデータを持つモジュールで `ApplyChanges` を呼び出すたびに、変更を出力するために使用されるコピーを除き、そのモジュールのメタデータのすべてのコピーに対して同じデルタメタデータを使用して[IMetaDataEmit:: ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md)を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc94c-120">Whenever the debugger calls `ApplyChanges` on a module that has delta metadata, it should also call [IMetaDataEmit::ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) with the same delta metadata on all of its copies of that module’s metadata except for the copy used to emit the changes.</span></span> <span data-ttu-id="bc94c-121">メタデータのコピーが実際のメタデータと同期しなくなる場合、デバッガーは常にそのコピーを破棄して新しいコピーを取得できます。</span><span class="sxs-lookup"><span data-stu-id="bc94c-121">If a copy of the metadata somehow becomes out-of-sync with the actual metadata, the debugger can always throw away that copy and obtain a new copy.</span></span>  
  
 <span data-ttu-id="bc94c-122">`ApplyChanges` メソッドが失敗した場合、デバッグセッションは無効な状態にあり、再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc94c-122">If the `ApplyChanges` method fails, the debug session is in an invalid state and must be restarted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc94c-123">［要件］</span><span class="sxs-lookup"><span data-stu-id="bc94c-123">Requirements</span></span>  
 <span data-ttu-id="bc94c-124">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc94c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc94c-125">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc94c-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc94c-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc94c-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc94c-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc94c-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
