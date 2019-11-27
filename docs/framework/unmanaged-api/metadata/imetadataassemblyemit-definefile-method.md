---
title: IMetaDataAssemblyEmit::DefineFile メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type:
- apiref
ms.openlocfilehash: 0b7ca6f9878ed2fa2d90ea93e5101f0a66ec2d5e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440209"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="6ec79-102">IMetaDataAssemblyEmit::DefineFile メソッド</span><span class="sxs-lookup"><span data-stu-id="6ec79-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="6ec79-103">このアセンブリが参照するアセンブリのメタデータを含む `File` メタデータ構造体を作成し、関連付けられたメタデータ トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="6ec79-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ec79-104">構文</span><span class="sxs-lookup"><span data-stu-id="6ec79-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,   
    [in]  const void     *pbHashValue,   
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ec79-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6ec79-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="6ec79-106">から使用するファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="6ec79-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="6ec79-107">からアセンブリに関連付けられているハッシュデータへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6ec79-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="6ec79-108">から`pbHashValue`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="6ec79-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="6ec79-109">からプロパティ設定を指定する `FileFlags` 値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="6ec79-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="6ec79-110">入出力返された `File` トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6ec79-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ec79-111">コメント</span><span class="sxs-lookup"><span data-stu-id="6ec79-111">Remarks</span></span>  
 <span data-ttu-id="6ec79-112">このアセンブリがビルドされた時点で、このアセンブリに含まれていたファイルごとに1つの `File` メタデータ構造を定義する必要があります。メタデータを含むファイルは除きます。</span><span class="sxs-lookup"><span data-stu-id="6ec79-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ec79-113">要件</span><span class="sxs-lookup"><span data-stu-id="6ec79-113">Requirements</span></span>  
 <span data-ttu-id="6ec79-114">**プラットフォーム:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ec79-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ec79-115">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="6ec79-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6ec79-116">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ec79-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6ec79-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ec79-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ec79-118">参照</span><span class="sxs-lookup"><span data-stu-id="6ec79-118">See also</span></span>

- [<span data-ttu-id="6ec79-119">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6ec79-119">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
