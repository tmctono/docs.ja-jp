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
ms.openlocfilehash: 5aa5d78faa8ca9261594e2a649b11088e1d78ee7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177871"
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="08465-102">IMetaDataAssemblyEmit::DefineManifestResource メソッド</span><span class="sxs-lookup"><span data-stu-id="08465-102">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>
<span data-ttu-id="08465-103">指定したマニフェスト リソースのメタデータを含む `ManifestResource` 構造体を作成し、関連付けられたメタデータ トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="08465-103">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08465-104">構文</span><span class="sxs-lookup"><span data-stu-id="08465-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,
    [in] mdToken                tkImplementation,
    [in] DWORD                  dwOffset,
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08465-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="08465-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="08465-106">[in]リソースの名前。</span><span class="sxs-lookup"><span data-stu-id="08465-106">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="08465-107">[in]型`mdtFile`のメタデータ トークン、または`mdtAssemblyRef`リソース プロバイダーにマップされるメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="08465-107">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="08465-108">NULL 値は、メタデータが埋め込まれているファイルがリソース プロバイダーであることを示します。</span><span class="sxs-lookup"><span data-stu-id="08465-108">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="08465-109">[in]ファイル内のリソースの先頭へのオフセット。</span><span class="sxs-lookup"><span data-stu-id="08465-109">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="08465-110">スタンドアロン ファイルのリソースの場合、これは常に 0 になります。</span><span class="sxs-lookup"><span data-stu-id="08465-110">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="08465-111">リソースが PE (ポータブル実行可能ファイル) ファイルに埋め込まれている場合、これは cor.h ヘッダー ファイルで指定された場所から開始されるリソース BLOB のオフセットです。</span><span class="sxs-lookup"><span data-stu-id="08465-111">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="08465-112">[in]リソース定義のプロパティ設定を指定するフラグ値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="08465-112">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="08465-113">[アウト]返されたメタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="08465-113">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08465-114">解説</span><span class="sxs-lookup"><span data-stu-id="08465-114">Remarks</span></span>  
 <span data-ttu-id="08465-115">アセンブリ`ManifestResource`のファイルごとに実装されるリソースごとに、1 つのメタデータ構造を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08465-115">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08465-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="08465-116">Requirements</span></span>  
 <span data-ttu-id="08465-117">**プラットフォーム:**[「システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08465-117">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08465-118">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="08465-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="08465-119">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="08465-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="08465-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08465-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08465-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="08465-121">See also</span></span>

- [<span data-ttu-id="08465-122">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="08465-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
