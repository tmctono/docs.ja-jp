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
ms.openlocfilehash: e5eb735acac73d694a0719c206bd22711a8c0333
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437542"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="bd90e-102">IMetaDataImport::GetInterfaceImplProps メソッド</span><span class="sxs-lookup"><span data-stu-id="bd90e-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="bd90e-103">指定したメソッドを実装する <xref:System.Type> のメタデータトークンへのポインターと、そのメソッドを宣言するインターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="bd90e-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="bd90e-104">構文</span><span class="sxs-lookup"><span data-stu-id="bd90e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd90e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bd90e-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="bd90e-106">からクラスとインターフェイストークンを返すメソッドを表すメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="bd90e-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="bd90e-107">入出力メソッドを実装するクラスを表すメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="bd90e-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="bd90e-108">入出力実装されたメソッドを定義するインターフェイスを表すメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="bd90e-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="bd90e-109">コメント</span><span class="sxs-lookup"><span data-stu-id="bd90e-109">Remarks</span></span>

 <span data-ttu-id="bd90e-110">`iImpl` の値を取得するには、 [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md)メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="bd90e-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>
 
 <span data-ttu-id="bd90e-111">たとえば、クラスの `mdTypeDef` トークン値が0x02000007 で、型にトークンが含まれている3つのインターフェイスを実装しているとします。</span><span class="sxs-lookup"><span data-stu-id="bd90e-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span> 

- <span data-ttu-id="bd90e-112">0x02000003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="bd90e-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="bd90e-113">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="bd90e-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="bd90e-114">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="bd90e-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="bd90e-115">概念的には、この情報は次のようにインターフェイス実装テーブルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="bd90e-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="bd90e-116">行番号</span><span class="sxs-lookup"><span data-stu-id="bd90e-116">Row number</span></span> | <span data-ttu-id="bd90e-117">クラストークン</span><span class="sxs-lookup"><span data-stu-id="bd90e-117">Class token</span></span> | <span data-ttu-id="bd90e-118">インターフェイストークン</span><span class="sxs-lookup"><span data-stu-id="bd90e-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="bd90e-119">4</span><span class="sxs-lookup"><span data-stu-id="bd90e-119">4</span></span>          |             |                 |
| <span data-ttu-id="bd90e-120">5</span><span class="sxs-lookup"><span data-stu-id="bd90e-120">5</span></span>          | <span data-ttu-id="bd90e-121">02000007</span><span class="sxs-lookup"><span data-stu-id="bd90e-121">02000007</span></span>    | <span data-ttu-id="bd90e-122">02000003</span><span class="sxs-lookup"><span data-stu-id="bd90e-122">02000003</span></span>        |
| <span data-ttu-id="bd90e-123">6</span><span class="sxs-lookup"><span data-stu-id="bd90e-123">6</span></span>          | <span data-ttu-id="bd90e-124">02000007</span><span class="sxs-lookup"><span data-stu-id="bd90e-124">02000007</span></span>    | <span data-ttu-id="bd90e-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="bd90e-125">0100000A</span></span>        |
| <span data-ttu-id="bd90e-126">7</span><span class="sxs-lookup"><span data-stu-id="bd90e-126">7</span></span>          |             |                 |
| <span data-ttu-id="bd90e-127">8</span><span class="sxs-lookup"><span data-stu-id="bd90e-127">8</span></span>          | <span data-ttu-id="bd90e-128">02000007</span><span class="sxs-lookup"><span data-stu-id="bd90e-128">02000007</span></span>    | <span data-ttu-id="bd90e-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="bd90e-129">0200001C</span></span>        |

<span data-ttu-id="bd90e-130">これは、トークンが4バイトの値であることを思い出してください。</span><span class="sxs-lookup"><span data-stu-id="bd90e-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="bd90e-131">下位3バイトは、行番号 (RID) を保持します。</span><span class="sxs-lookup"><span data-stu-id="bd90e-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="bd90e-132">上位バイトは、`mdtInterfaceImpl`のトークンの種類 (0x09) を保持します。</span><span class="sxs-lookup"><span data-stu-id="bd90e-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="bd90e-133">`GetInterfaceImplProps` は、`iImpl` 引数で指定したトークンを持つ行に保持されている情報を返します。</span><span class="sxs-lookup"><span data-stu-id="bd90e-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span> 
  
## <a name="requirements"></a><span data-ttu-id="bd90e-134">要件</span><span class="sxs-lookup"><span data-stu-id="bd90e-134">Requirements</span></span>  
 <span data-ttu-id="bd90e-135">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd90e-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd90e-136">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="bd90e-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd90e-137">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="bd90e-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bd90e-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd90e-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd90e-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd90e-139">See also</span></span>

- [<span data-ttu-id="bd90e-140">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bd90e-140">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="bd90e-141">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bd90e-141">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
