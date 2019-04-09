---
title: IMetaDataImport::FindField メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 88cd08b4290739808079bc8ecb713a5c5ea96584
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172563"
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="c0234-102">IMetaDataImport::FindField メソッド</span><span class="sxs-lookup"><span data-stu-id="c0234-102">IMetaDataImport::FindField Method</span></span>
<span data-ttu-id="c0234-103">囲まれたフィールドの FieldDef にポインターをトークン取得を指定した<xref:System.Type>指定した名前とメタデータ シグネチャを持つとします。</span><span class="sxs-lookup"><span data-stu-id="c0234-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0234-104">構文</span><span class="sxs-lookup"><span data-stu-id="c0234-104">Syntax</span></span>  
  
```  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0234-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0234-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="c0234-106">[in]クラスまたはインターフェイスを検索するフィールドを囲む TypeDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="c0234-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="c0234-107">この値が場合`mdTokenNil`、グローバル変数の検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0234-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="c0234-108">[in]検索するフィールドの名前。</span><span class="sxs-lookup"><span data-stu-id="c0234-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="c0234-109">[in]フィールドのバイナリ メタデータ シグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c0234-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="c0234-110">[in]バイト サイズ`pvSigBlob`します。</span><span class="sxs-lookup"><span data-stu-id="c0234-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="c0234-111">[out]一致する FieldDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c0234-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0234-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="c0234-112">Remarks</span></span>  
 <span data-ttu-id="c0234-113">外側のクラスまたはインターフェイスを使用して、フィールドを指定する (`td`)、その名前 (`szName`)、および必要に応じてその署名 (`pvSigBlob`)。</span><span class="sxs-lookup"><span data-stu-id="c0234-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="c0234-114">渡される署名`FindField`生成された現在のスコープで特定のスコープにバインドされるためです。</span><span class="sxs-lookup"><span data-stu-id="c0234-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="c0234-115">署名は、外側のクラスまたは値の型を識別するトークンを埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="c0234-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="c0234-116">(トークンは、ローカルの TypeDef テーブルへのインデックス) です。</span><span class="sxs-lookup"><span data-stu-id="c0234-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="c0234-117">現在のスコープのコンテキスト外にあるランタイムのシグネチャを作成してへの入力としてその署名を使用することはできません`FindField`します。</span><span class="sxs-lookup"><span data-stu-id="c0234-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 `FindField` <span data-ttu-id="c0234-118">クラスまたはインターフェイス内で直接定義されたフィールドのみを検索します。継承されたフィールドは検索しません。</span><span class="sxs-lookup"><span data-stu-id="c0234-118">finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0234-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="c0234-119">Requirements</span></span>  
 <span data-ttu-id="c0234-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0234-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0234-121">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c0234-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c0234-122">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c0234-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="c0234-123">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="c0234-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c0234-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0234-124">See also</span></span>

- [<span data-ttu-id="c0234-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0234-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c0234-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0234-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
