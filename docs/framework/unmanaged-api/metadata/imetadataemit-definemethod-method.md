---
title: IMetaDataEmit::DefineMethod メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type:
- apiref
ms.openlocfilehash: d4f3c95428d6f0f8807e284c5b54582428176511
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177675"
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="e29ca-102">IMetaDataEmit::DefineMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="e29ca-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="e29ca-103">指定したシグネチャを持つメソッドまたはグローバル関数の定義を作成し、そのメソッド定義にトークンを返します。</span><span class="sxs-lookup"><span data-stu-id="e29ca-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e29ca-104">構文</span><span class="sxs-lookup"><span data-stu-id="e29ca-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethod (
    [in]  mdTypeDef         td,
    [in]  LPCWSTR           szName,
    [in]  DWORD             dwMethodFlags,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [in]  ULONG             ulCodeRVA,
    [in]  DWORD             dwImplFlags,
    [out] mdMethodDef      *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e29ca-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e29ca-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="e29ca-106">[in]メソッド`mdTypedef`の親クラスまたは親インターフェイスのトークン。</span><span class="sxs-lookup"><span data-stu-id="e29ca-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="e29ca-107">グローバル`td`関数`mdTokenNil`を定義する場合は、 に設定します。</span><span class="sxs-lookup"><span data-stu-id="e29ca-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="e29ca-108">[in]ユニコードのメンバー名。</span><span class="sxs-lookup"><span data-stu-id="e29ca-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="e29ca-109">[in]メソッドまたはグローバル関数の属性を指定する[CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="e29ca-109">[in] A value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="e29ca-110">[in]メソッド シグネチャ。</span><span class="sxs-lookup"><span data-stu-id="e29ca-110">[in] The method signature.</span></span> <span data-ttu-id="e29ca-111">署名は、指定されたとおりに永続化されます。</span><span class="sxs-lookup"><span data-stu-id="e29ca-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="e29ca-112">パラメーターに追加情報を指定する必要がある場合は、[メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="e29ca-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="e29ca-113">[in]のバイト数`pvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="e29ca-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="e29ca-114">[in]コードのアドレス。</span><span class="sxs-lookup"><span data-stu-id="e29ca-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="e29ca-115">[in]メソッドの実装機能を指定する[CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)列挙の値。</span><span class="sxs-lookup"><span data-stu-id="e29ca-115">[in] A value of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="e29ca-116">[アウト]メンバー トークン。</span><span class="sxs-lookup"><span data-stu-id="e29ca-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e29ca-117">解説</span><span class="sxs-lookup"><span data-stu-id="e29ca-117">Remarks</span></span>  
 <span data-ttu-id="e29ca-118">メタデータ API は、メソッドを、パラメーターで指定されている特定の外側のクラスまたはインターフェイスに対して呼び出し元が出力する順序と`td`同じ順序で永続化します。</span><span class="sxs-lookup"><span data-stu-id="e29ca-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="e29ca-119">使用および特定のパラメータ設定`DefineMethod`に関する追加情報は以下に示します。</span><span class="sxs-lookup"><span data-stu-id="e29ca-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="e29ca-120">V テーブル内のスロット</span><span class="sxs-lookup"><span data-stu-id="e29ca-120">Slots in the V-table</span></span>  
 <span data-ttu-id="e29ca-121">ランタイムはメソッド定義を使用して v テーブル スロットを設定します。</span><span class="sxs-lookup"><span data-stu-id="e29ca-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="e29ca-122">COM インターフェイス レイアウトとのパリティを保持するなど、1 つ以上のスロットをスキップする必要がある場合は、v テーブル内のスロットまたはスロットを取り込むダミー メソッドが定義されます。`dwMethodFlags``mdRTSpecialName`[を、CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)列挙体の値に設定し、名前を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="e29ca-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="e29ca-123">_VtblGap\<*シーケンス*>\<番号\_*カウントの数*></span><span class="sxs-lookup"><span data-stu-id="e29ca-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>
  
 <span data-ttu-id="e29ca-124">シーケンス*番号*はメソッドのシーケンス番号で *、CountOfSlots*は v テーブルでスキップするスロットの数です。</span><span class="sxs-lookup"><span data-stu-id="e29ca-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="e29ca-125">*CountOfSlots を*省略すると、1 が想定されます。</span><span class="sxs-lookup"><span data-stu-id="e29ca-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="e29ca-126">これらのダミー メソッドは、マネージ コードまたはアンマネージ コードから呼び出す可能性があり、マネージ コードまたはアンマネージ コードから呼び出そうとすると例外が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e29ca-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="e29ca-127">その唯一の目的は、ランタイムが COM 統合用に生成する v テーブル内の領域を取り込むためです。</span><span class="sxs-lookup"><span data-stu-id="e29ca-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="e29ca-128">メソッドの重複</span><span class="sxs-lookup"><span data-stu-id="e29ca-128">Duplicate Methods</span></span>  
 <span data-ttu-id="e29ca-129">重複するメソッドを定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="e29ca-129">You should not define duplicate methods.</span></span> <span data-ttu-id="e29ca-130">つまり`DefineMethod`、 `td`、および`wzName``pvSig`パラメーターの値の重複したセットを呼び出す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e29ca-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="e29ca-131">(これらの 3 つのパラメーターを一緒にメソッドを一意に定義します。</span><span class="sxs-lookup"><span data-stu-id="e29ca-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="e29ca-132">ただし、メソッド定義の 1 つに対して、パラメーターにビットを`mdPrivateScope`設定する場合は、重複するトリプル`dwMethodFlags`を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e29ca-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="e29ca-133">(ビット`mdPrivateScope`は、コンパイラがこのメソッド定義への参照を出力しないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e29ca-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="e29ca-134">メソッド実装情報</span><span class="sxs-lookup"><span data-stu-id="e29ca-134">Method Implementation Information</span></span>  
 <span data-ttu-id="e29ca-135">メソッドの実装に関する情報は、メソッドが宣言された時点では不明な場合があります。</span><span class="sxs-lookup"><span data-stu-id="e29ca-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="e29ca-136">したがって、 を呼び出すときに、`ulCodeRVA`パラメータ`dwImplFlags`に値を`DefineMethod`渡す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e29ca-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="e29ca-137">値は、必要に応じて[後で IMetaDataEmit:::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md)または[IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)を介して指定できます。</span><span class="sxs-lookup"><span data-stu-id="e29ca-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="e29ca-138">プラットフォーム呼び出し (PInvoke) や COM 相互運用シナリオなど、状況によっては、メソッド本体は提供されず`ulCodeRVA`、0 に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e29ca-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="e29ca-139">このような場合、ランタイムは実装を検索するため、メソッドを抽象としてタグ付けしないでください。</span><span class="sxs-lookup"><span data-stu-id="e29ca-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="e29ca-140">PInvoke のメソッドの定義</span><span class="sxs-lookup"><span data-stu-id="e29ca-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="e29ca-141">PInvoke を通じて呼び出されるアンマネージ関数ごとに、ターゲットアンマネージ関数を表すマネージ メソッドを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e29ca-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="e29ca-142">マネージ メソッドを定義するには、PInvoke の使用方法に応じて、いくつかのパラメーターを特定の値に設定して使用`DefineMethod`します。</span><span class="sxs-lookup"><span data-stu-id="e29ca-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
- <span data-ttu-id="e29ca-143">True PInvoke - アンマネージ DLL に存在する外部アンマネージ メソッドの呼び出しを伴います。</span><span class="sxs-lookup"><span data-stu-id="e29ca-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
- <span data-ttu-id="e29ca-144">ローカル PInvoke - 現在のマネージ モジュールに埋め込まれているネイティブアンマネージ メソッドの呼び出しを含みます。</span><span class="sxs-lookup"><span data-stu-id="e29ca-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="e29ca-145">パラメータの設定は次の表のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e29ca-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="e29ca-146">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e29ca-146">Parameter</span></span>|<span data-ttu-id="e29ca-147">真の PInvoke の値</span><span class="sxs-lookup"><span data-stu-id="e29ca-147">Values for true PInvoke</span></span>|<span data-ttu-id="e29ca-148">ローカル PInvoke の値</span><span class="sxs-lookup"><span data-stu-id="e29ca-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="e29ca-149">設定`mdStatic`;クリア`mdSynchronized`および`mdAbstract`.</span><span class="sxs-lookup"><span data-stu-id="e29ca-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="e29ca-150">有効なマネージ型のパラメーターを持つ有効な共通言語ランタイム (CLR) メソッドシグネチャ。</span><span class="sxs-lookup"><span data-stu-id="e29ca-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="e29ca-151">有効なマネージ型のパラメーターを持つ有効な CLR メソッド シグネチャ。</span><span class="sxs-lookup"><span data-stu-id="e29ca-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="e29ca-152">0</span><span class="sxs-lookup"><span data-stu-id="e29ca-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="e29ca-153">`miCil` と `miManaged` を設定します。</span><span class="sxs-lookup"><span data-stu-id="e29ca-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="e29ca-154">`miNative` と `miUnmanaged` を設定します。</span><span class="sxs-lookup"><span data-stu-id="e29ca-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e29ca-155">必要条件</span><span class="sxs-lookup"><span data-stu-id="e29ca-155">Requirements</span></span>  
 <span data-ttu-id="e29ca-156">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e29ca-156">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e29ca-157">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="e29ca-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e29ca-158">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="e29ca-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e29ca-159">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e29ca-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e29ca-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="e29ca-160">See also</span></span>

- [<span data-ttu-id="e29ca-161">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e29ca-161">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e29ca-162">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e29ca-162">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
