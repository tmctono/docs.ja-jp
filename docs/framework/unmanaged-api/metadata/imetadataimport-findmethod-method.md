---
title: IMetaDataImport::FindMethod メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
ms.openlocfilehash: 53b3d94e8b1e273fcbc041d25a5bf586a12735c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177252"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="dca0b-102">IMetaDataImport::FindMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="dca0b-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="dca0b-103">指定した名前とメタデータ シグネチャを持つメソッドの MethodDef トークン<xref:System.Type>へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="dca0b-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dca0b-104">構文</span><span class="sxs-lookup"><span data-stu-id="dca0b-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dca0b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dca0b-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="dca0b-106">[in]検索`mdTypeDef`するメンバーを囲む型 (クラスまたはインターフェイス) のトークン。</span><span class="sxs-lookup"><span data-stu-id="dca0b-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="dca0b-107">この値が`mdTokenNil`の場合、グローバル関数の検索が行われます。</span><span class="sxs-lookup"><span data-stu-id="dca0b-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="dca0b-108">[in]検索するメソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="dca0b-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="dca0b-109">[in]メソッドのバイナリ メタデータ シグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="dca0b-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="dca0b-110">[in]のサイズ (バイト`pvSigBlob`単位)</span><span class="sxs-lookup"><span data-stu-id="dca0b-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="dca0b-111">[アウト]一致する MethodDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="dca0b-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dca0b-112">解説</span><span class="sxs-lookup"><span data-stu-id="dca0b-112">Remarks</span></span>  
 <span data-ttu-id="dca0b-113">メソッドは、外側のクラスまたはインターフェイス (`td`) を使用して`szName`指定し、その名前 (`pvSigBlob`) 、およびオプションでそのシグネチャ ( ) を使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="dca0b-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="dca0b-114">クラスまたはインターフェイス内に同じ名前のメソッドが複数存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="dca0b-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="dca0b-115">その場合は、メソッドのシグネチャを渡して一意の一致を見つけます。</span><span class="sxs-lookup"><span data-stu-id="dca0b-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="dca0b-116">渡された署名は`FindMethod`、特定のスコープにバインドされているため、現在のスコープで生成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dca0b-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="dca0b-117">シグネチャは、外側のクラスまたは値の型を識別するトークンを埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="dca0b-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="dca0b-118">トークンは、ローカルの TypeDef テーブルへのインデックスです。</span><span class="sxs-lookup"><span data-stu-id="dca0b-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="dca0b-119">現在のスコープのコンテキストの外部でランタイム シグネチャを作成し、そのシグネチャを`FindMethod`入力として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="dca0b-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="dca0b-120">`FindMethod`は、クラスまたはインターフェイスで直接定義されたメソッドのみを検索します。継承されたメソッドは見つかりません。</span><span class="sxs-lookup"><span data-stu-id="dca0b-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dca0b-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="dca0b-121">Requirements</span></span>  
 <span data-ttu-id="dca0b-122">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dca0b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dca0b-123">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="dca0b-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dca0b-124">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="dca0b-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dca0b-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dca0b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dca0b-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="dca0b-126">See also</span></span>

- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="dca0b-127">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dca0b-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="dca0b-128">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dca0b-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
