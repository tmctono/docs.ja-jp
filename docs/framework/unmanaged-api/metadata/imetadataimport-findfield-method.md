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
ms.openlocfilehash: 11ea6e468909ea42e38bdc7b76c60c460c98025e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503667"
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="d404d-102">IMetaDataImport::FindField メソッド</span><span class="sxs-lookup"><span data-stu-id="d404d-102">IMetaDataImport::FindField Method</span></span>
<span data-ttu-id="d404d-103">指定した <xref:System.Type> と指定した名前とメタデータシグネチャを持つフィールドの FieldDef トークンへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="d404d-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d404d-104">構文</span><span class="sxs-lookup"><span data-stu-id="d404d-104">Syntax</span></span>  
  
```cpp  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d404d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d404d-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="d404d-106">から検索対象のフィールドを囲むクラスまたはインターフェイスの TypeDef トークン。</span><span class="sxs-lookup"><span data-stu-id="d404d-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="d404d-107">この値がの場合 `mdTokenNil` 、グローバル変数に対して参照が行われます。</span><span class="sxs-lookup"><span data-stu-id="d404d-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="d404d-108">から検索するフィールドの名前。</span><span class="sxs-lookup"><span data-stu-id="d404d-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="d404d-109">からフィールドのバイナリメタデータシグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d404d-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="d404d-110">からのサイズ (バイト単位) `pvSigBlob` 。</span><span class="sxs-lookup"><span data-stu-id="d404d-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="d404d-111">入出力一致する FieldDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d404d-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d404d-112">解説</span><span class="sxs-lookup"><span data-stu-id="d404d-112">Remarks</span></span>  
 <span data-ttu-id="d404d-113">フィールドは、外側のクラスまたはインターフェイス ( `td` )、その名前 ( `szName` )、および必要に応じてシグネチャ () を使用して指定し `pvSigBlob` ます。</span><span class="sxs-lookup"><span data-stu-id="d404d-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="d404d-114">署名は特定のスコープにバインドされるため、に渡されるシグネチャは、 `FindField` 現在のスコープで生成される必要があります。</span><span class="sxs-lookup"><span data-stu-id="d404d-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="d404d-115">署名には、外側のクラスまたは値の型を識別するトークンを埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="d404d-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="d404d-116">(トークンは、ローカルの TypeDef テーブルのインデックスです)。</span><span class="sxs-lookup"><span data-stu-id="d404d-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="d404d-117">現在のスコープのコンテキスト外でランタイムシグネチャを作成し、その署名をへの入力として使用することはできません `FindField` 。</span><span class="sxs-lookup"><span data-stu-id="d404d-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 <span data-ttu-id="d404d-118">`FindField`クラスまたはインターフェイスで直接定義されたフィールドのみを検索します。継承されたフィールドは見つかりません。</span><span class="sxs-lookup"><span data-stu-id="d404d-118">`FindField` finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d404d-119">要件</span><span class="sxs-lookup"><span data-stu-id="d404d-119">Requirements</span></span>  
 <span data-ttu-id="d404d-120">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d404d-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d404d-121">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="d404d-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d404d-122">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="d404d-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d404d-123">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d404d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d404d-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="d404d-124">See also</span></span>

- [<span data-ttu-id="d404d-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d404d-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="d404d-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d404d-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
