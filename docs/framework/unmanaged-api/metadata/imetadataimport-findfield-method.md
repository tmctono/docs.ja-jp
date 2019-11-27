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
ms.openlocfilehash: 842d6c0deb90bc45cb59454fb30fcc3544d742f1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437941"
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="722bc-102">IMetaDataImport::FindField メソッド</span><span class="sxs-lookup"><span data-stu-id="722bc-102">IMetaDataImport::FindField Method</span></span>
<span data-ttu-id="722bc-103">指定した <xref:System.Type> で囲まれ、指定された名前とメタデータシグネチャを持つフィールドの FieldDef トークンへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="722bc-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="722bc-104">構文</span><span class="sxs-lookup"><span data-stu-id="722bc-104">Syntax</span></span>  
  
```cpp  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="722bc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="722bc-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="722bc-106">から検索対象のフィールドを囲むクラスまたはインターフェイスの TypeDef トークン。</span><span class="sxs-lookup"><span data-stu-id="722bc-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="722bc-107">この値が `mdTokenNil`場合は、グローバル変数に対して参照が行われます。</span><span class="sxs-lookup"><span data-stu-id="722bc-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="722bc-108">から検索するフィールドの名前。</span><span class="sxs-lookup"><span data-stu-id="722bc-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="722bc-109">からフィールドのバイナリメタデータシグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="722bc-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="722bc-110">から`pvSigBlob`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="722bc-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="722bc-111">入出力一致する FieldDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="722bc-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="722bc-112">コメント</span><span class="sxs-lookup"><span data-stu-id="722bc-112">Remarks</span></span>  
 <span data-ttu-id="722bc-113">フィールドは、外側のクラスまたはインターフェイス (`td`)、その名前 (`szName`)、および必要に応じて署名 (`pvSigBlob`) を使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="722bc-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="722bc-114">シグネチャは特定のスコープにバインドされているため、`FindField` に渡される署名は、現在のスコープで生成される必要があります。</span><span class="sxs-lookup"><span data-stu-id="722bc-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="722bc-115">署名には、外側のクラスまたは値の型を識別するトークンを埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="722bc-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="722bc-116">(トークンは、ローカルの TypeDef テーブルのインデックスです)。</span><span class="sxs-lookup"><span data-stu-id="722bc-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="722bc-117">現在のスコープのコンテキスト外でランタイムシグネチャを作成し、その署名を `FindField`の入力として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="722bc-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 <span data-ttu-id="722bc-118">`FindField` は、クラスまたはインターフェイスで直接定義されたフィールドのみを検索します。継承されたフィールドは見つかりません。</span><span class="sxs-lookup"><span data-stu-id="722bc-118">`FindField` finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="722bc-119">要件</span><span class="sxs-lookup"><span data-stu-id="722bc-119">Requirements</span></span>  
 <span data-ttu-id="722bc-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="722bc-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="722bc-121">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="722bc-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="722bc-122">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="722bc-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="722bc-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="722bc-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="722bc-124">参照</span><span class="sxs-lookup"><span data-stu-id="722bc-124">See also</span></span>

- [<span data-ttu-id="722bc-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="722bc-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="722bc-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="722bc-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
