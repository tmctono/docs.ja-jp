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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab0e28bd21b66f370a1a1e82359fe474574fd7bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987963"
---
# <a name="icordebugmodule2applychanges-method"></a><span data-ttu-id="c6b00-102">ICorDebugModule2::ApplyChanges メソッド</span><span class="sxs-lookup"><span data-stu-id="c6b00-102">ICorDebugModule2::ApplyChanges Method</span></span>
<span data-ttu-id="c6b00-103">実行中のプロセスにメタデータの変更と Microsoft intermediate language (MSIL) コードの変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="c6b00-103">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6b00-104">構文</span><span class="sxs-lookup"><span data-stu-id="c6b00-104">Syntax</span></span>  
  
```  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6b00-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c6b00-105">Parameters</span></span>  
 `cbMetadata`  
 <span data-ttu-id="c6b00-106">[in]デルタのメタデータのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="c6b00-106">[in] Size, in bytes, of the delta metadata.</span></span>  
  
 `pbMetadata`  
 <span data-ttu-id="c6b00-107">[in]デルタのメタデータを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="c6b00-107">[in] Buffer that contains the delta metadata.</span></span> <span data-ttu-id="c6b00-108">バッファーのアドレスから返される、 [imetadataemit 2::savedeltatomemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="c6b00-108">The address of the buffer is returned from the [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) method.</span></span>  
  
 <span data-ttu-id="c6b00-109">MSIL コードの先頭からの相対メタデータ内の相対仮想アドレス (Rva) があります。</span><span class="sxs-lookup"><span data-stu-id="c6b00-109">The relative virtual addresses (RVAs) in the metadata should be relative to the start of the MSIL code.</span></span>  
  
 `cbIL`  
 <span data-ttu-id="c6b00-110">[in]デルタの MSIL コードのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="c6b00-110">[in] Size, in bytes, of the delta MSIL code.</span></span>  
  
 `pbIL`  
 <span data-ttu-id="c6b00-111">[in]更新された MSIL コードを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="c6b00-111">[in] Buffer that contains the updated MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6b00-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="c6b00-112">Remarks</span></span>  
 <span data-ttu-id="c6b00-113">`pbMetadata`パラメーターは、特別なデルタ メタデータ形式では (によって出力として[imetadataemit 2::savedeltatomemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md))。</span><span class="sxs-lookup"><span data-stu-id="c6b00-113">The `pbMetadata` parameter is in a special delta metadata format (as output by [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)).</span></span> <span data-ttu-id="c6b00-114">`pbMetadata` ベースとして前のメタデータを受け取り、そのベースに適用する個々 の変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="c6b00-114">`pbMetadata` takes previous metadata as a base and describes individual changes to apply to that base.</span></span>  
  
 <span data-ttu-id="c6b00-115">これに対し、 `pbIL[`] パラメーターが新しい、更新されたメソッドの MSIL を含むし、そのメソッドの以前の MSIL を完全に置き換えるものでは</span><span class="sxs-lookup"><span data-stu-id="c6b00-115">In contrast, the `pbIL[`] parameter contains the new MSIL for the updated method, and is meant to completely replace the previous MSIL for that method</span></span>  
  
 <span data-ttu-id="c6b00-116">デバッガーのメモリ内で、デルタ MSIL とメタデータが作成されると、デバッガーが呼び出す`ApplyChanges`共通言語ランタイム (CLR) に変更を送信します。</span><span class="sxs-lookup"><span data-stu-id="c6b00-116">When the delta MSIL and the metadata have been created in the debugger’s memory, the debugger calls `ApplyChanges` to send the changes into the common language runtime (CLR).</span></span> <span data-ttu-id="c6b00-117">ランタイムは、そのメタデータ テーブルを更新、新しい MSIL をプロセスに配置し、新しい MSIL のジャストイン タイム (JIT) コンパイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="c6b00-117">The runtime updates its metadata tables, places the new MSIL into the process, and sets up a just-in-time (JIT) compilation of the new MSIL.</span></span> <span data-ttu-id="c6b00-118">変更が適用されている場合、デバッガーを呼び出す必要があります[imetadataemit 2::resetenclog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) [次へ] の編集セッションを準備します。</span><span class="sxs-lookup"><span data-stu-id="c6b00-118">When the changes have been applied, the debugger should call [IMetaDataEmit2::ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) to prepare for the next editing session.</span></span> <span data-ttu-id="c6b00-119">デバッガーは、プロセスを続行することがあります。</span><span class="sxs-lookup"><span data-stu-id="c6b00-119">The debugger may then continue the process.</span></span>  
  
 <span data-ttu-id="c6b00-120">デバッガーを呼び出すたびに`ApplyChanges`デルタのメタデータを含むモジュールの場合に呼び出す必要もあります[imetadataemit::applyeditandcontinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md)コピーを除き、そのモジュールのメタデータのコピーのすべてに同じデルタ メタデータを持つ変更内容を出力するために使用します。</span><span class="sxs-lookup"><span data-stu-id="c6b00-120">Whenever the debugger calls `ApplyChanges` on a module that has delta metadata, it should also call [IMetaDataEmit::ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) with the same delta metadata on all of its copies of that module’s metadata except for the copy used to emit the changes.</span></span> <span data-ttu-id="c6b00-121">場合は、メタデータのコピーは、非同期の何らかの方法でになります。 実際のメタデータとデバッガー常にそのコピーを破棄して新しいコピーを取得します。</span><span class="sxs-lookup"><span data-stu-id="c6b00-121">If a copy of the metadata somehow becomes out-of-sync with the actual metadata, the debugger can always throw away that copy and obtain a new copy.</span></span>  
  
 <span data-ttu-id="c6b00-122">場合、`ApplyChanges`メソッドが失敗した場合は、デバッグ セッションが無効の状態と、再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6b00-122">If the `ApplyChanges` method fails, the debug session is in an invalid state and must be restarted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6b00-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="c6b00-123">Requirements</span></span>  
 <span data-ttu-id="c6b00-124">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6b00-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6b00-125">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6b00-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6b00-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6b00-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6b00-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6b00-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
