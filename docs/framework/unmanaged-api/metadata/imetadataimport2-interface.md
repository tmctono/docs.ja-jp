---
title: IMetaDataImport2 インターフェイス
ms.date: 03/30/2017
api_name:
- IMetaDataImport2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2
helpviewer_keywords:
- IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type:
- apiref
ms.openlocfilehash: 0fd7915ef46899bdce8312bc6e8a466167e26382
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429211"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="bf6dd-102">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf6dd-102">IMetaDataImport2 Interface</span></span>
<span data-ttu-id="bf6dd-103">[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)インターフェイスを拡張して、ジェネリック型を処理する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="bf6dd-103">Extends the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bf6dd-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="bf6dd-104">Methods</span></span>  
  
|<span data-ttu-id="bf6dd-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="bf6dd-105">Method</span></span>|<span data-ttu-id="bf6dd-106">説明</span><span class="sxs-lookup"><span data-stu-id="bf6dd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bf6dd-107">EnumGenericParamConstraints メソッド</span><span class="sxs-lookup"><span data-stu-id="bf6dd-107">EnumGenericParamConstraints Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="bf6dd-108">指定したトークンによって表されるジェネリックパラメーターに関連付けられているジェネリックパラメーター制約の配列の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="bf6dd-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="bf6dd-109">EnumGenericParams メソッド</span><span class="sxs-lookup"><span data-stu-id="bf6dd-109">EnumGenericParams Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="bf6dd-110">指定した TypeDef または MethodDef トークンに関連付けられているジェネリックパラメータートークンの配列の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="bf6dd-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="bf6dd-111">EnumMethodSpecs メソッド</span><span class="sxs-lookup"><span data-stu-id="bf6dd-111">EnumMethodSpecs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="bf6dd-112">指定した MethodDef または MemberRef トークンに関連付けられている MethodSpec トークンの配列の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="bf6dd-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="bf6dd-113">GetGenericParamConstraintProps メソッド</span><span class="sxs-lookup"><span data-stu-id="bf6dd-113">GetGenericParamConstraintProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="bf6dd-114">指定された制約トークンによって表されるジェネリックパラメーター制約に関連付けられているメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="bf6dd-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="bf6dd-115">GetGenericParamProps メソッド</span><span class="sxs-lookup"><span data-stu-id="bf6dd-115">GetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="bf6dd-116">指定したトークンによって表されるジェネリックパラメーターに関連付けられているメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="bf6dd-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="bf6dd-117">GetMethodSpecProps メソッド</span><span class="sxs-lookup"><span data-stu-id="bf6dd-117">GetMethodSpecProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="bf6dd-118">指定した MethodSpec トークンによって参照されるメソッドのメタデータシグネチャを取得します。</span><span class="sxs-lookup"><span data-stu-id="bf6dd-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="bf6dd-119">GetPEKind メソッド</span><span class="sxs-lookup"><span data-stu-id="bf6dd-119">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|<span data-ttu-id="bf6dd-120">移植可能な実行可能 (PE) ファイルのコードの性質を示す値を取得します。通常は、現在のメタデータスコープで定義されている DLL または EXE ファイルです。</span><span class="sxs-lookup"><span data-stu-id="bf6dd-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="bf6dd-121">GetVersionString メソッド</span><span class="sxs-lookup"><span data-stu-id="bf6dd-121">GetVersionString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|<span data-ttu-id="bf6dd-122">アセンブリのビルドに使用されたランタイムのバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="bf6dd-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bf6dd-123">要件</span><span class="sxs-lookup"><span data-stu-id="bf6dd-123">Requirements</span></span>  
 <span data-ttu-id="bf6dd-124">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf6dd-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf6dd-125">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="bf6dd-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bf6dd-126">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="bf6dd-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bf6dd-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf6dd-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf6dd-128">参照</span><span class="sxs-lookup"><span data-stu-id="bf6dd-128">See also</span></span>

- <xref:System.Reflection.PortableExecutableKinds>
- [<span data-ttu-id="bf6dd-129">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf6dd-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="bf6dd-130">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf6dd-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
