---
title: IMetaDataAssemblyEmit::DefineManifestResource メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineManifestResource
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type:
- apiref
ms.openlocfilehash: 83170815f4aa65988bb6a6394bd466a0ba376ebf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432058"
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="8d354-102">IMetaDataAssemblyEmit::DefineManifestResource メソッド</span><span class="sxs-lookup"><span data-stu-id="8d354-102">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>
<span data-ttu-id="8d354-103">指定したマニフェスト リソースのメタデータを含む `ManifestResource` 構造体を作成し、関連付けられたメタデータ トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="8d354-103">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d354-104">構文</span><span class="sxs-lookup"><span data-stu-id="8d354-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,   
    [in] mdToken                tkImplementation,   
    [in] DWORD                  dwOffset,   
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d354-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8d354-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="8d354-106">からリソースの名前。</span><span class="sxs-lookup"><span data-stu-id="8d354-106">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="8d354-107">からリソースプロバイダーにマップされる `mdtFile` または `mdtAssemblyRef` 型のメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="8d354-107">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="8d354-108">NULL 値は、メタデータが埋め込まれているファイルがリソースプロバイダーであることを示します。</span><span class="sxs-lookup"><span data-stu-id="8d354-108">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="8d354-109">からファイル内のリソースの先頭へのオフセット。</span><span class="sxs-lookup"><span data-stu-id="8d354-109">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="8d354-110">スタンドアロンファイルのリソースの場合、この値は常に0になります。</span><span class="sxs-lookup"><span data-stu-id="8d354-110">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="8d354-111">リソースが PE (ポータブル実行可能ファイル) ファイルに埋め込まれている場合、これはリソース BLOB のオフセットになります。これは、cor ヘッダーファイルで指定された場所から開始されます。</span><span class="sxs-lookup"><span data-stu-id="8d354-111">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="8d354-112">からリソース定義のプロパティ設定を指定するフラグ値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="8d354-112">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="8d354-113">入出力返されたメタデータトークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8d354-113">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d354-114">コメント</span><span class="sxs-lookup"><span data-stu-id="8d354-114">Remarks</span></span>  
 <span data-ttu-id="8d354-115">各アセンブリのファイルに実装されている各リソースに対して、1つの `ManifestResource` メタデータ構造を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d354-115">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d354-116">要件</span><span class="sxs-lookup"><span data-stu-id="8d354-116">Requirements</span></span>  
 <span data-ttu-id="8d354-117">**プラットフォーム:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d354-117">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d354-118">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="8d354-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8d354-119">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="8d354-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8d354-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d354-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d354-121">参照</span><span class="sxs-lookup"><span data-stu-id="8d354-121">See also</span></span>

- [<span data-ttu-id="8d354-122">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8d354-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
