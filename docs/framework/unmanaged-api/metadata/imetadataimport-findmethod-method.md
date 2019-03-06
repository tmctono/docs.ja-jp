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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 857ea06ad8aba2a6de87bdf670ad0462a2f7dde1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487287"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="1f72b-102">IMetaDataImport::FindMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="1f72b-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="1f72b-103">囲まれたメソッドの methoddef にポインターをトークン取得を指定した<xref:System.Type>指定した名前とメタデータ シグネチャを持つとします。</span><span class="sxs-lookup"><span data-stu-id="1f72b-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f72b-104">構文</span><span class="sxs-lookup"><span data-stu-id="1f72b-104">Syntax</span></span>  
  
```  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f72b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1f72b-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="1f72b-106">[in]`mdTypeDef`を検索するメンバーを囲む型 (クラスまたはインターフェイス) のトークン。</span><span class="sxs-lookup"><span data-stu-id="1f72b-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="1f72b-107">この値が場合`mdTokenNil`、グローバル関数、検索を実行し、します。</span><span class="sxs-lookup"><span data-stu-id="1f72b-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="1f72b-108">[in]検索するメソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="1f72b-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="1f72b-109">[in]メソッドのバイナリ メタデータ シグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1f72b-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="1f72b-110">[in]バイト サイズ`pvSigBlob`します。</span><span class="sxs-lookup"><span data-stu-id="1f72b-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="1f72b-111">[out]一致する MethodDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1f72b-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f72b-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="1f72b-112">Remarks</span></span>  
 <span data-ttu-id="1f72b-113">外側のクラスまたはインターフェイスを使用して、メソッドを指定する (`td`)、その名前 (`szName`)、および必要に応じてその署名 (`pvSigBlob`)。</span><span class="sxs-lookup"><span data-stu-id="1f72b-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="1f72b-114">クラスまたはインターフェイスで同じ名前の複数のメソッドである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1f72b-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="1f72b-115">その場合は、一意の一致を検索するメソッドのシグネチャを渡します。</span><span class="sxs-lookup"><span data-stu-id="1f72b-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="1f72b-116">渡される署名`FindMethod`生成された現在のスコープで特定のスコープにバインドされるためです。</span><span class="sxs-lookup"><span data-stu-id="1f72b-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="1f72b-117">署名は、外側のクラスまたは値の型を識別するトークンを埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="1f72b-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="1f72b-118">トークンは、ローカルの TypeDef テーブルへのインデックスです。</span><span class="sxs-lookup"><span data-stu-id="1f72b-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="1f72b-119">現在のスコープのコンテキスト外にある実行時シグネチャを作成してを入力としてその署名を使用することはできません`FindMethod`します。</span><span class="sxs-lookup"><span data-stu-id="1f72b-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="1f72b-120">`FindMethod` クラスまたはインターフェイス内で直接定義されたメソッドのみを検索します継承されたメソッドは検索しません。</span><span class="sxs-lookup"><span data-stu-id="1f72b-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f72b-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="1f72b-121">Requirements</span></span>  
 <span data-ttu-id="1f72b-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f72b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f72b-123">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1f72b-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1f72b-124">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="1f72b-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1f72b-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f72b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f72b-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f72b-126">See also</span></span>
- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="1f72b-127">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1f72b-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="1f72b-128">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1f72b-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
