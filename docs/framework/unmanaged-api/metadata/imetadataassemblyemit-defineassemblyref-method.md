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
ms.openlocfilehash: c88b7a401a19b1bd0e02edab7ef7bbee1372199e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432083"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a><span data-ttu-id="ce141-102">IMetaDataAssemblyEmit::DefineAssemblyRef メソッド</span><span class="sxs-lookup"><span data-stu-id="ce141-102">IMetaDataAssemblyEmit::DefineAssemblyRef Method</span></span>
<span data-ttu-id="ce141-103">このアセンブリが参照するアセンブリのメタデータを含む `AssemblyRef` 構造体を作成し、関連付けられたメタデータ トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="ce141-103">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce141-104">構文</span><span class="sxs-lookup"><span data-stu-id="ce141-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ce141-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ce141-105">Parameters</span></span>  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="ce141-106">から参照アセンブリの発行元の公開キー。</span><span class="sxs-lookup"><span data-stu-id="ce141-106">[in] The public key of the publisher of the referenced assembly.</span></span> <span data-ttu-id="ce141-107">ヘルパー関数[StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)を使用して、このパラメーターとして渡す公開キーのハッシュを取得できます。</span><span class="sxs-lookup"><span data-stu-id="ce141-107">The helper function [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) can be used to get the hash of the public key to pass as this parameter.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="ce141-108">から`pbPublicKeyOrToken`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="ce141-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="ce141-109">からユーザーが判読できる、アセンブリのテキスト名。</span><span class="sxs-lookup"><span data-stu-id="ce141-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="ce141-110">この値は、1024文字を超えないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce141-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="ce141-111">から参照されたアセンブリのバージョン、プラットフォーム、およびロケール情報を格納している ASSEMBLYMETADATA インスタンス。</span><span class="sxs-lookup"><span data-stu-id="ce141-111">[in] An ASSEMBLYMETADATA instance that contains the version, platform and locale information of the referenced assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="ce141-112">から参照アセンブリに関連付けられているハッシュデータ。</span><span class="sxs-lookup"><span data-stu-id="ce141-112">[in] The hash data associated with the referenced assembly.</span></span> <span data-ttu-id="ce141-113">省略可。</span><span class="sxs-lookup"><span data-stu-id="ce141-113">Optional.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="ce141-114">から`pbHashValue`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="ce141-114">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="ce141-115">から実行エンジンの動作に影響を与える[Corassemblyflags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="ce141-115">[in] A bitwise combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that influence the behavior of the execution engine.</span></span>  
  
 `pmdar`  
 <span data-ttu-id="ce141-116">入出力返された `AssemblyRef` メタデータトークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ce141-116">[out] A pointer to the returned `AssemblyRef` metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce141-117">コメント</span><span class="sxs-lookup"><span data-stu-id="ce141-117">Remarks</span></span>  
 <span data-ttu-id="ce141-118">このアセンブリが参照するアセンブリごとに1つの `AssemblyRef` メタデータ構造を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce141-118">One `AssemblyRef` metadata structure must be defined for each assembly that this assembly references.</span></span>  
  
 <span data-ttu-id="ce141-119">実行時には、参照されたアセンブリの詳細がアセンブリリゾルバーに渡され、"ビルド済み" の情報を表すことが示されます。</span><span class="sxs-lookup"><span data-stu-id="ce141-119">At run time, the details of a referenced assembly are passed to the assembly resolver with an indication that they represent the "as built" information.</span></span> <span data-ttu-id="ce141-120">次に、アセンブリリゾルバーがポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="ce141-120">The assembly resolver then applies policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce141-121">要件</span><span class="sxs-lookup"><span data-stu-id="ce141-121">Requirements</span></span>  
 <span data-ttu-id="ce141-122">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce141-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce141-123">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="ce141-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce141-124">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="ce141-124">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ce141-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce141-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce141-126">参照</span><span class="sxs-lookup"><span data-stu-id="ce141-126">See also</span></span>

- [<span data-ttu-id="ce141-127">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ce141-127">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
