---
title: IMetaDataImport::GetInterfaceImplProps メソッド
ms.date: 02/25/2019
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a4305b94d785a764671a2d73f43facefd0da0e6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782369"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="147f7-102">IMetaDataImport::GetInterfaceImplProps メソッド</span><span class="sxs-lookup"><span data-stu-id="147f7-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="147f7-103">メタデータ トークンへのポインターを取得、<xref:System.Type>指定されたメソッドを実装して、そのメソッドを宣言するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="147f7-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="147f7-104">構文</span><span class="sxs-lookup"><span data-stu-id="147f7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="147f7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="147f7-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="147f7-106">[in]クラスとインターフェイスのトークンを返すメソッドを表すメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="147f7-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="147f7-107">[out]メソッドを実装するクラスを表すメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="147f7-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="147f7-108">[out]実装されたメソッドを定義するインターフェイスを表すメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="147f7-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="147f7-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="147f7-109">Remarks</span></span>

 <span data-ttu-id="147f7-110">値を取得する`iImpl`呼び出すことによって、 [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="147f7-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>
 
 <span data-ttu-id="147f7-111">たとえば、クラスがあること、 `mdTypeDef` 0x02000007 という値と型を持つトークンがある 3 つのインターフェイスを実装するトークンします。</span><span class="sxs-lookup"><span data-stu-id="147f7-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span> 

- <span data-ttu-id="147f7-112">0x02000003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="147f7-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="147f7-113">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="147f7-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="147f7-114">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="147f7-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="147f7-115">概念的には、この情報は、インターフェイスの実装としてテーブルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="147f7-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="147f7-116">行番号</span><span class="sxs-lookup"><span data-stu-id="147f7-116">Row number</span></span> | <span data-ttu-id="147f7-117">クラスのトークン</span><span class="sxs-lookup"><span data-stu-id="147f7-117">Class token</span></span> | <span data-ttu-id="147f7-118">トークンをインターフェイスします。</span><span class="sxs-lookup"><span data-stu-id="147f7-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="147f7-119">4</span><span class="sxs-lookup"><span data-stu-id="147f7-119">4</span></span>          |             |                 |
| <span data-ttu-id="147f7-120">5</span><span class="sxs-lookup"><span data-stu-id="147f7-120">5</span></span>          | <span data-ttu-id="147f7-121">02000007</span><span class="sxs-lookup"><span data-stu-id="147f7-121">02000007</span></span>    | <span data-ttu-id="147f7-122">02000003</span><span class="sxs-lookup"><span data-stu-id="147f7-122">02000003</span></span>        |
| <span data-ttu-id="147f7-123">6</span><span class="sxs-lookup"><span data-stu-id="147f7-123">6</span></span>          | <span data-ttu-id="147f7-124">02000007</span><span class="sxs-lookup"><span data-stu-id="147f7-124">02000007</span></span>    | <span data-ttu-id="147f7-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="147f7-125">0100000A</span></span>        |
| <span data-ttu-id="147f7-126">7</span><span class="sxs-lookup"><span data-stu-id="147f7-126">7</span></span>          |             |                 |
| <span data-ttu-id="147f7-127">8</span><span class="sxs-lookup"><span data-stu-id="147f7-127">8</span></span>          | <span data-ttu-id="147f7-128">02000007</span><span class="sxs-lookup"><span data-stu-id="147f7-128">02000007</span></span>    | <span data-ttu-id="147f7-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="147f7-129">0200001C</span></span>        |

<span data-ttu-id="147f7-130">トークンが 4 バイトの値を思い出してください。</span><span class="sxs-lookup"><span data-stu-id="147f7-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="147f7-131">下位 3 バイトは、行番号を保持または削除します。</span><span class="sxs-lookup"><span data-stu-id="147f7-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="147f7-132">上位バイトを保持するトークンの種類 – の 0x09`mdtInterfaceImpl`します。</span><span class="sxs-lookup"><span data-stu-id="147f7-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="147f7-133">`GetInterfaceImplProps` 行で指定したトークンに保持されている情報を返します、`iImpl`引数。</span><span class="sxs-lookup"><span data-stu-id="147f7-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span> 
  
## <a name="requirements"></a><span data-ttu-id="147f7-134">必要条件</span><span class="sxs-lookup"><span data-stu-id="147f7-134">Requirements</span></span>  
 <span data-ttu-id="147f7-135">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="147f7-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="147f7-136">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="147f7-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="147f7-137">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="147f7-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="147f7-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="147f7-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="147f7-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="147f7-139">See also</span></span>

- [<span data-ttu-id="147f7-140">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="147f7-140">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="147f7-141">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="147f7-141">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
