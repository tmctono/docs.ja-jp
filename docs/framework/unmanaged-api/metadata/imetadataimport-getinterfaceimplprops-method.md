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
ms.openlocfilehash: 1c9d9647084aa729817eeeb17ee3f5cd320c0d29
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491245"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="94e27-102">IMetaDataImport::GetInterfaceImplProps メソッド</span><span class="sxs-lookup"><span data-stu-id="94e27-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="94e27-103">指定したメソッドを実装するのメタデータトークンへのポインター <xref:System.Type> と、そのメソッドを宣言するインターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="94e27-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="94e27-104">構文</span><span class="sxs-lookup"><span data-stu-id="94e27-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94e27-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="94e27-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="94e27-106">からクラスとインターフェイストークンを返すメソッドを表すメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="94e27-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="94e27-107">入出力メソッドを実装するクラスを表すメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="94e27-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="94e27-108">入出力実装されたメソッドを定義するインターフェイスを表すメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="94e27-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="94e27-109">解説</span><span class="sxs-lookup"><span data-stu-id="94e27-109">Remarks</span></span>

 <span data-ttu-id="94e27-110">の値を取得する `iImpl` には、 [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md)メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="94e27-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>

 <span data-ttu-id="94e27-111">たとえば、クラスの `mdTypeDef` トークン値が0x02000007 で、型がトークンを持つ3つのインターフェイスを実装しているとします。</span><span class="sxs-lookup"><span data-stu-id="94e27-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span>

- <span data-ttu-id="94e27-112">0x02000003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="94e27-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="94e27-113">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="94e27-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="94e27-114">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="94e27-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="94e27-115">概念的には、この情報は次のようにインターフェイス実装テーブルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="94e27-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="94e27-116">行番号</span><span class="sxs-lookup"><span data-stu-id="94e27-116">Row number</span></span> | <span data-ttu-id="94e27-117">クラストークン</span><span class="sxs-lookup"><span data-stu-id="94e27-117">Class token</span></span> | <span data-ttu-id="94e27-118">インターフェイストークン</span><span class="sxs-lookup"><span data-stu-id="94e27-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="94e27-119">4</span><span class="sxs-lookup"><span data-stu-id="94e27-119">4</span></span>          |             |                 |
| <span data-ttu-id="94e27-120">5</span><span class="sxs-lookup"><span data-stu-id="94e27-120">5</span></span>          | <span data-ttu-id="94e27-121">02000007</span><span class="sxs-lookup"><span data-stu-id="94e27-121">02000007</span></span>    | <span data-ttu-id="94e27-122">02000003</span><span class="sxs-lookup"><span data-stu-id="94e27-122">02000003</span></span>        |
| <span data-ttu-id="94e27-123">6</span><span class="sxs-lookup"><span data-stu-id="94e27-123">6</span></span>          | <span data-ttu-id="94e27-124">02000007</span><span class="sxs-lookup"><span data-stu-id="94e27-124">02000007</span></span>    | <span data-ttu-id="94e27-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="94e27-125">0100000A</span></span>        |
| <span data-ttu-id="94e27-126">7</span><span class="sxs-lookup"><span data-stu-id="94e27-126">7</span></span>          |             |                 |
| <span data-ttu-id="94e27-127">8</span><span class="sxs-lookup"><span data-stu-id="94e27-127">8</span></span>          | <span data-ttu-id="94e27-128">02000007</span><span class="sxs-lookup"><span data-stu-id="94e27-128">02000007</span></span>    | <span data-ttu-id="94e27-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="94e27-129">0200001C</span></span>        |

<span data-ttu-id="94e27-130">これは、トークンが4バイトの値であることを思い出してください。</span><span class="sxs-lookup"><span data-stu-id="94e27-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="94e27-131">下位3バイトは、行番号 (RID) を保持します。</span><span class="sxs-lookup"><span data-stu-id="94e27-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="94e27-132">上位バイトは、のトークンの種類 (0x09) を保持し `mdtInterfaceImpl` ます。</span><span class="sxs-lookup"><span data-stu-id="94e27-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="94e27-133">`GetInterfaceImplProps`引数で指定したトークンを持つ行に保持されている情報を返し `iImpl` ます。</span><span class="sxs-lookup"><span data-stu-id="94e27-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="94e27-134">要件</span><span class="sxs-lookup"><span data-stu-id="94e27-134">Requirements</span></span>  
 <span data-ttu-id="94e27-135">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94e27-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94e27-136">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="94e27-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="94e27-137">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="94e27-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="94e27-138">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94e27-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94e27-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="94e27-139">See also</span></span>

- [<span data-ttu-id="94e27-140">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="94e27-140">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="94e27-141">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="94e27-141">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
