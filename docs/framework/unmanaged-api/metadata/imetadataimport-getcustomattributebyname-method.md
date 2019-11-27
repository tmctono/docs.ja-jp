---
title: IMetaDataImport::GetCustomAttributeByName メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type:
- apiref
ms.openlocfilehash: bd7ba7ff10918e5953ea8ae89a60af3115af48a3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437686"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="d6b86-102">IMetaDataImport::GetCustomAttributeByName メソッド</span><span class="sxs-lookup"><span data-stu-id="d6b86-102">IMetaDataImport::GetCustomAttributeByName Method</span></span>
<span data-ttu-id="d6b86-103">名前と所有者を指定して、カスタム属性を取得します。</span><span class="sxs-lookup"><span data-stu-id="d6b86-103">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6b86-104">構文</span><span class="sxs-lookup"><span data-stu-id="d6b86-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6b86-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d6b86-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="d6b86-106">からカスタム属性を所有するオブジェクトを表すメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="d6b86-106">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="d6b86-107">からカスタム属性の名前。</span><span class="sxs-lookup"><span data-stu-id="d6b86-107">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="d6b86-108">入出力カスタム属性の値であるデータの配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d6b86-108">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="d6b86-109">入出力\*`ppData`に返されるデータのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="d6b86-109">[out] The size in bytes of the data returned in \*`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6b86-110">コメント</span><span class="sxs-lookup"><span data-stu-id="d6b86-110">Remarks</span></span>  
 <span data-ttu-id="d6b86-111">同じ所有者に対して複数のカスタム属性を定義することは有効です。同じ名前を持つ場合もあります。</span><span class="sxs-lookup"><span data-stu-id="d6b86-111">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="d6b86-112">ただし、`GetCustomAttributeByName` は1つのインスタンスのみを返します。</span><span class="sxs-lookup"><span data-stu-id="d6b86-112">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="d6b86-113">(`GetCustomAttributeByName` は、最初に見つかったインスタンスを返します)。カスタム属性のすべてのインスタンスを検索するには、 [IMetaDataImport:: EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md)メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d6b86-113">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6b86-114">要件</span><span class="sxs-lookup"><span data-stu-id="d6b86-114">Requirements</span></span>  
 <span data-ttu-id="d6b86-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6b86-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6b86-116">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="d6b86-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d6b86-117">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="d6b86-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d6b86-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6b86-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6b86-119">参照</span><span class="sxs-lookup"><span data-stu-id="d6b86-119">See also</span></span>

- [<span data-ttu-id="d6b86-120">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d6b86-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d6b86-121">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d6b86-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
