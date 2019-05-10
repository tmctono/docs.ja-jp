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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4879af90aa06515a95b4d15f039ff3c2b1a88f62
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665015"
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="de575-102">IMetaDataEmit::DefineMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="de575-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="de575-103">指定したシグネチャを持つメソッドまたはグローバル関数の定義を作成し、そのメソッドの定義にトークンを返します。</span><span class="sxs-lookup"><span data-stu-id="de575-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de575-104">構文</span><span class="sxs-lookup"><span data-stu-id="de575-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="de575-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="de575-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="de575-106">[in]`mdTypedef`親クラスまたはメソッドの親インターフェイスのトークン。</span><span class="sxs-lookup"><span data-stu-id="de575-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="de575-107">設定`td`に`mdTokenNil`グローバル関数を定義する場合、します。</span><span class="sxs-lookup"><span data-stu-id="de575-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="de575-108">[in]Unicode でメンバーの名前。</span><span class="sxs-lookup"><span data-stu-id="de575-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="de575-109">[in]値、 [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)メソッドまたはグローバル関数の属性を指定する列挙体。</span><span class="sxs-lookup"><span data-stu-id="de575-109">[in] A value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="de575-110">[in]メソッド シグネチャ。</span><span class="sxs-lookup"><span data-stu-id="de575-110">[in] The method signature.</span></span> <span data-ttu-id="de575-111">提供される、署名が保持されます。</span><span class="sxs-lookup"><span data-stu-id="de575-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="de575-112">任意のパラメーターの追加情報を指定する必要がある場合、 [imetadataemit::setparamprops](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="de575-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="de575-113">[in]内のバイト数`pvSigBlob`します。</span><span class="sxs-lookup"><span data-stu-id="de575-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="de575-114">[in]コードのアドレス。</span><span class="sxs-lookup"><span data-stu-id="de575-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="de575-115">[in]値、 [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)メソッドの実装の機能を指定する列挙体。</span><span class="sxs-lookup"><span data-stu-id="de575-115">[in] A value of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="de575-116">[out]メンバー トークンです。</span><span class="sxs-lookup"><span data-stu-id="de575-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de575-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="de575-117">Remarks</span></span>  
 <span data-ttu-id="de575-118">メタデータ API が、呼び出し元が指定された外側のクラスまたはインターフェイスで指定された出力に、同じ順序でメソッドを保持するには、`td`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="de575-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="de575-119">使用に関する追加情報`DefineMethod`し、特定のパラメーターの設定のとおりです。</span><span class="sxs-lookup"><span data-stu-id="de575-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="de575-120">V テーブル内のスロット</span><span class="sxs-lookup"><span data-stu-id="de575-120">Slots in the V-table</span></span>  
 <span data-ttu-id="de575-121">ランタイムでは、メソッドの定義を使用して、v テーブル スロットを設定します。</span><span class="sxs-lookup"><span data-stu-id="de575-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="de575-122">1 つまたは複数のスロットがスキップする必要がある場合、COM インターフェイスのレイアウトでパリティを保持するか、ダミー メソッドが定義されて v テーブル内のスロットを占有するには設定、`dwMethodFlags`に、`mdRTSpecialName`の値、 [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)列挙型として名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="de575-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="de575-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span><span class="sxs-lookup"><span data-stu-id="de575-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>
  
 <span data-ttu-id="de575-124">場所*SequenceNumber*メソッドのシーケンス番号と*CountOfSlots* v テーブルでスキップするスロットの数です。</span><span class="sxs-lookup"><span data-stu-id="de575-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="de575-125">場合*CountOfSlots*は省略すると、1 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="de575-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="de575-126">これらのダミー メソッドは、マネージまたはアンマネージ コードから呼び出すことでありしようとすると、これらをマネージまたはアンマネージ コードから呼び出すには、例外が生成されます。</span><span class="sxs-lookup"><span data-stu-id="de575-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="de575-127">その唯一の目的では、COM の統合ランタイムが生成する v テーブルの領域を占有します。</span><span class="sxs-lookup"><span data-stu-id="de575-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="de575-128">メソッドが重複しています</span><span class="sxs-lookup"><span data-stu-id="de575-128">Duplicate Methods</span></span>  
 <span data-ttu-id="de575-129">重複するメソッドを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de575-129">You should not define duplicate methods.</span></span> <span data-ttu-id="de575-130">つまり、呼び出す必要はありません`DefineMethod`重複する一連の値の`td`、 `wzName`、および`pvSig`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="de575-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="de575-131">(これら 3 つのパラメーター、メソッドを一意に定義します。)。</span><span class="sxs-lookup"><span data-stu-id="de575-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="de575-132">メソッド定義の 1 つが設定されている、重複する 3 つの要素を使用するただし、`mdPrivateScope`ビット、`dwMethodFlags`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="de575-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="de575-133">(、`mdPrivateScope`ビットは、コンパイラはこのメソッドの定義への参照を出力しないことを意味します)。</span><span class="sxs-lookup"><span data-stu-id="de575-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="de575-134">メソッドの実装に関する情報</span><span class="sxs-lookup"><span data-stu-id="de575-134">Method Implementation Information</span></span>  
 <span data-ttu-id="de575-135">メソッドの実装の詳細については多くの場合、メソッドの宣言時に呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="de575-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="de575-136">そのため、必要はありませんで値を渡す、`ulCodeRVA`と`dwImplFlags`を呼び出すときに、パラメーター`DefineMethod`します。</span><span class="sxs-lookup"><span data-stu-id="de575-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="de575-137">後でを通じて値を指定することができます[imetadataemit::setmethodimplflags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md)または[imetadataemit::setrva](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)必要に応じて、します。</span><span class="sxs-lookup"><span data-stu-id="de575-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="de575-138">プラットフォーム呼び出し (PInvoke) または COM 相互運用のシナリオなど、いくつかの状況でメソッドの本体を指定できませんと`ulCodeRVA`0 に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de575-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="de575-139">このような場合は、メソッドはタグが付いていない抽象として、ランタイムは、実装を見つけるため。</span><span class="sxs-lookup"><span data-stu-id="de575-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="de575-140">PInvoke のメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="de575-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="de575-141">PInvoke によって呼び出される各アンマネージ関数では、非管理対象の関数を表すマネージ メソッドを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de575-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="de575-142">マネージ メソッドを定義するには、使用`DefineMethod`PInvoke を使用する方法に応じて、特定の値に設定されているパラメーターの一部で。</span><span class="sxs-lookup"><span data-stu-id="de575-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
- <span data-ttu-id="de575-143">PInvoke の true - アンマネージ DLL 内にある外部のアンマネージ メソッドの呼び出しが含まれます。</span><span class="sxs-lookup"><span data-stu-id="de575-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
- <span data-ttu-id="de575-144">ローカルの PInvoke - には、現在のマネージ モジュール内に埋め込まれているネイティブのアンマネージ メソッドの呼び出しが含まれます。</span><span class="sxs-lookup"><span data-stu-id="de575-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="de575-145">パラメーターの設定は、次の表に付与されます。</span><span class="sxs-lookup"><span data-stu-id="de575-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="de575-146">パラメーター</span><span class="sxs-lookup"><span data-stu-id="de575-146">Parameter</span></span>|<span data-ttu-id="de575-147">PInvoke が true の値</span><span class="sxs-lookup"><span data-stu-id="de575-147">Values for true PInvoke</span></span>|<span data-ttu-id="de575-148">ローカルの PInvoke の値</span><span class="sxs-lookup"><span data-stu-id="de575-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="de575-149">設定`mdStatic`クリア;`mdSynchronized`と`mdAbstract`します。</span><span class="sxs-lookup"><span data-stu-id="de575-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="de575-150">有効な共通言語ランタイム (CLR) メソッド署名で有効なパラメーターはマネージ型です。</span><span class="sxs-lookup"><span data-stu-id="de575-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="de575-151">有効なパラメーターを持つ有効な CLR メソッド署名はマネージ型です。</span><span class="sxs-lookup"><span data-stu-id="de575-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="de575-152">0</span><span class="sxs-lookup"><span data-stu-id="de575-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="de575-153">設定`miCil`と`miManaged`します。</span><span class="sxs-lookup"><span data-stu-id="de575-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="de575-154">設定`miNative`と`miUnmanaged`します。</span><span class="sxs-lookup"><span data-stu-id="de575-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="de575-155">必要条件</span><span class="sxs-lookup"><span data-stu-id="de575-155">Requirements</span></span>  
 <span data-ttu-id="de575-156">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="de575-156">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de575-157">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="de575-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="de575-158">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="de575-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="de575-159">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de575-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de575-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="de575-160">See also</span></span>

- [<span data-ttu-id="de575-161">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de575-161">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="de575-162">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de575-162">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
