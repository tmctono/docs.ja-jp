---
title: IMetaDataAssemblyEmit::DefineAssemblyRef メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssemblyRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c150f4bda901627fc21ed54926c3cf959bb829a3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776304"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a><span data-ttu-id="d660a-102">IMetaDataAssemblyEmit::DefineAssemblyRef メソッド</span><span class="sxs-lookup"><span data-stu-id="d660a-102">IMetaDataAssemblyEmit::DefineAssemblyRef Method</span></span>
<span data-ttu-id="d660a-103">このアセンブリが参照するアセンブリのメタデータを含む `AssemblyRef` 構造体を作成し、関連付けられたメタデータ トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="d660a-103">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d660a-104">構文</span><span class="sxs-lookup"><span data-stu-id="d660a-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineAssemblyRef (  
    [in]  void                *pbPublicKeyOrToken,  
    [in]  ULONG               cbPublicKeyOrToken,  
    [in]  LPCWSTR             szName,  
    [in]  ASSEMBLYMETADATA    pMetaData,  
    [in]  void                *pbHashValue,  
    [in]  ULONG               cbHashValue,  
    [in]  DWORD               dwAssemblyRefFlags,  
    [out] mdAssemblyRef       *pmdar  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d660a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d660a-105">Parameters</span></span>  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="d660a-106">[in]参照先アセンブリの発行者の公開キー。</span><span class="sxs-lookup"><span data-stu-id="d660a-106">[in] The public key of the publisher of the referenced assembly.</span></span> <span data-ttu-id="d660a-107">ヘルパー関数[StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)このパラメーターとして渡すパブリック キーのハッシュを取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d660a-107">The helper function [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) can be used to get the hash of the public key to pass as this parameter.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="d660a-108">[in]バイト サイズ`pbPublicKeyOrToken`します。</span><span class="sxs-lookup"><span data-stu-id="d660a-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="d660a-109">[in]アセンブリの人間が判読できるテキストの名前。</span><span class="sxs-lookup"><span data-stu-id="d660a-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="d660a-110">この値は 1024 文字を超えない必要があります。</span><span class="sxs-lookup"><span data-stu-id="d660a-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="d660a-111">[in]参照アセンブリのバージョン、プラットフォーム、ロケール情報を含む ASSEMBLYMETADATA インスタンス。</span><span class="sxs-lookup"><span data-stu-id="d660a-111">[in] An ASSEMBLYMETADATA instance that contains the version, platform and locale information of the referenced assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="d660a-112">[in]参照先のアセンブリに関連付けられたデータをハッシュします。</span><span class="sxs-lookup"><span data-stu-id="d660a-112">[in] The hash data associated with the referenced assembly.</span></span> <span data-ttu-id="d660a-113">任意。</span><span class="sxs-lookup"><span data-stu-id="d660a-113">Optional.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="d660a-114">[in]バイト サイズ`pbHashValue`します。</span><span class="sxs-lookup"><span data-stu-id="d660a-114">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="d660a-115">[in]ビットごとの組み合わせ[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)実行エンジンの動作を制御する値。</span><span class="sxs-lookup"><span data-stu-id="d660a-115">[in] A bitwise combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that influence the behavior of the execution engine.</span></span>  
  
 `pmdar`  
 <span data-ttu-id="d660a-116">[out]返されたポインター`AssemblyRef`メタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="d660a-116">[out] A pointer to the returned `AssemblyRef` metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d660a-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="d660a-117">Remarks</span></span>  
 <span data-ttu-id="d660a-118">1 つ`AssemblyRef`このアセンブリを参照する各アセンブリのメタデータ構造を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d660a-118">One `AssemblyRef` metadata structure must be defined for each assembly that this assembly references.</span></span>  
  
 <span data-ttu-id="d660a-119">実行時に、参照先アセンブリの詳細については、"ビルド"と情報を表すことを示す値をアセンブリの競合回避モジュールに渡されます。</span><span class="sxs-lookup"><span data-stu-id="d660a-119">At run time, the details of a referenced assembly are passed to the assembly resolver with an indication that they represent the "as built" information.</span></span> <span data-ttu-id="d660a-120">アセンブリ リゾルバーは、ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="d660a-120">The assembly resolver then applies policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d660a-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="d660a-121">Requirements</span></span>  
 <span data-ttu-id="d660a-122">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d660a-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d660a-123">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d660a-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d660a-124">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="d660a-124">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d660a-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d660a-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d660a-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="d660a-126">See also</span></span>

- [<span data-ttu-id="d660a-127">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d660a-127">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
