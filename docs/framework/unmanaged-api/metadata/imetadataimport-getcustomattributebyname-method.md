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
ms.openlocfilehash: e6921a0f6420546ba1e866e37a7a7cb129a77c67
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491460"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="8647d-102">IMetaDataImport::GetCustomAttributeByName メソッド</span><span class="sxs-lookup"><span data-stu-id="8647d-102">IMetaDataImport::GetCustomAttributeByName Method</span></span>
<span data-ttu-id="8647d-103">名前と所有者を指定して、カスタム属性を取得します。</span><span class="sxs-lookup"><span data-stu-id="8647d-103">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8647d-104">構文</span><span class="sxs-lookup"><span data-stu-id="8647d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8647d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8647d-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="8647d-106">からカスタム属性を所有するオブジェクトを表すメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="8647d-106">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="8647d-107">からカスタム属性の名前。</span><span class="sxs-lookup"><span data-stu-id="8647d-107">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="8647d-108">入出力カスタム属性の値であるデータの配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8647d-108">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="8647d-109">入出力\* で返されるデータのサイズ (バイト単位) `ppData` 。</span><span class="sxs-lookup"><span data-stu-id="8647d-109">[out] The size in bytes of the data returned in \*`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8647d-110">解説</span><span class="sxs-lookup"><span data-stu-id="8647d-110">Remarks</span></span>  
 <span data-ttu-id="8647d-111">同じ所有者に対して複数のカスタム属性を定義することは有効です。同じ名前を持つ場合もあります。</span><span class="sxs-lookup"><span data-stu-id="8647d-111">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="8647d-112">ただし、は `GetCustomAttributeByName` 1 つのインスタンスのみを返します。</span><span class="sxs-lookup"><span data-stu-id="8647d-112">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="8647d-113">( `GetCustomAttributeByName` 最初に見つかったインスタンスを返します)。カスタム属性のすべてのインスタンスを検索するには、 [IMetaDataImport:: EnumCustomAttributes](imetadataimport-enumcustomattributes-method.md)メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8647d-113">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8647d-114">要件</span><span class="sxs-lookup"><span data-stu-id="8647d-114">Requirements</span></span>  
 <span data-ttu-id="8647d-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8647d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8647d-116">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="8647d-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8647d-117">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="8647d-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8647d-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8647d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8647d-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="8647d-119">See also</span></span>

- [<span data-ttu-id="8647d-120">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8647d-120">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="8647d-121">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8647d-121">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
