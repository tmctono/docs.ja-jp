---
title: IMetaDataImport2::EnumMethodSpecs メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
ms.openlocfilehash: 4a1de144163ec2b4952bd16b59fb1c92b706631b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428301"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="8f621-102">IMetaDataImport2::EnumMethodSpecs メソッド</span><span class="sxs-lookup"><span data-stu-id="8f621-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="8f621-103">指定した MethodDef または MemberRef トークンに関連付けられている MethodSpec トークンの配列の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="8f621-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f621-104">構文</span><span class="sxs-lookup"><span data-stu-id="8f621-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="8f621-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8f621-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8f621-106">[入力、出力]`rMethodSpecs`の列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8f621-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="8f621-107">からMethodSpec トークンを列挙するメソッドを表す MemberRef または MethodDef トークン。</span><span class="sxs-lookup"><span data-stu-id="8f621-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="8f621-108">`tk` の値が 0 (ゼロ) の場合、スコープ内のすべての MethodSpec トークンが列挙されます。</span><span class="sxs-lookup"><span data-stu-id="8f621-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="8f621-109">入出力列挙する MethodSpec トークンの配列。</span><span class="sxs-lookup"><span data-stu-id="8f621-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8f621-110">から`rMethodSpecs`に格納する、要求されたトークンの最大数。</span><span class="sxs-lookup"><span data-stu-id="8f621-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="8f621-111">入出力`rMethodSpecs`に格納された、返されたトークンの数。</span><span class="sxs-lookup"><span data-stu-id="8f621-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f621-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="8f621-112">Return Value</span></span>  
  
|<span data-ttu-id="8f621-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8f621-113">HRESULT</span></span>|<span data-ttu-id="8f621-114">説明</span><span class="sxs-lookup"><span data-stu-id="8f621-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8f621-115">`EnumMethodSpecs` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="8f621-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8f621-116">`phEnum` にメンバー要素がありません。</span><span class="sxs-lookup"><span data-stu-id="8f621-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="8f621-117">この場合、`pcMethodSpecs` は 0 (ゼロ) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8f621-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8f621-118">要件</span><span class="sxs-lookup"><span data-stu-id="8f621-118">Requirements</span></span>  
 <span data-ttu-id="8f621-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f621-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f621-120">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="8f621-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8f621-121">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f621-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8f621-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f621-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f621-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f621-123">See also</span></span>

- [<span data-ttu-id="8f621-124">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f621-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="8f621-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f621-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
