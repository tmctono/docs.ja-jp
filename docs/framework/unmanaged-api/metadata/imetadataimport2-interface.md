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
ms.openlocfilehash: fe9e87618291218a41e52f80198ce9068c9c56e2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490396"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="658ec-102">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="658ec-102">IMetaDataImport2 Interface</span></span>
<span data-ttu-id="658ec-103">[IMetaDataImport](imetadataimport-interface.md)インターフェイスを拡張して、ジェネリック型を処理する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="658ec-103">Extends the [IMetaDataImport](imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="658ec-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="658ec-104">Methods</span></span>  
  
|<span data-ttu-id="658ec-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="658ec-105">Method</span></span>|<span data-ttu-id="658ec-106">説明</span><span class="sxs-lookup"><span data-stu-id="658ec-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="658ec-107">EnumGenericParamConstraints メソッド</span><span class="sxs-lookup"><span data-stu-id="658ec-107">EnumGenericParamConstraints Method</span></span>](imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="658ec-108">指定したトークンによって表されるジェネリックパラメーターに関連付けられているジェネリックパラメーター制約の配列の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="658ec-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="658ec-109">EnumGenericParams メソッド</span><span class="sxs-lookup"><span data-stu-id="658ec-109">EnumGenericParams Method</span></span>](imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="658ec-110">指定した TypeDef または MethodDef トークンに関連付けられているジェネリックパラメータートークンの配列の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="658ec-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="658ec-111">EnumMethodSpecs メソッド</span><span class="sxs-lookup"><span data-stu-id="658ec-111">EnumMethodSpecs Method</span></span>](imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="658ec-112">指定した MethodDef または MemberRef トークンに関連付けられている MethodSpec トークンの配列の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="658ec-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="658ec-113">GetGenericParamConstraintProps メソッド</span><span class="sxs-lookup"><span data-stu-id="658ec-113">GetGenericParamConstraintProps Method</span></span>](imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="658ec-114">指定された制約トークンによって表されるジェネリックパラメーター制約に関連付けられているメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="658ec-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="658ec-115">GetGenericParamProps メソッド</span><span class="sxs-lookup"><span data-stu-id="658ec-115">GetGenericParamProps Method</span></span>](imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="658ec-116">指定したトークンによって表されるジェネリックパラメーターに関連付けられているメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="658ec-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="658ec-117">GetMethodSpecProps メソッド</span><span class="sxs-lookup"><span data-stu-id="658ec-117">GetMethodSpecProps Method</span></span>](imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="658ec-118">指定した MethodSpec トークンによって参照されるメソッドのメタデータシグネチャを取得します。</span><span class="sxs-lookup"><span data-stu-id="658ec-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="658ec-119">GetPEKind メソッド</span><span class="sxs-lookup"><span data-stu-id="658ec-119">GetPEKind Method</span></span>](imetadataimport2-getpekind-method.md)|<span data-ttu-id="658ec-120">移植可能な実行可能 (PE) ファイルのコードの性質を示す値を取得します。通常は、現在のメタデータスコープで定義されている DLL または EXE ファイルです。</span><span class="sxs-lookup"><span data-stu-id="658ec-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="658ec-121">GetVersionString メソッド</span><span class="sxs-lookup"><span data-stu-id="658ec-121">GetVersionString Method</span></span>](imetadataimport2-getversionstring-method.md)|<span data-ttu-id="658ec-122">アセンブリのビルドに使用されたランタイムのバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="658ec-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="658ec-123">要件</span><span class="sxs-lookup"><span data-stu-id="658ec-123">Requirements</span></span>  
 <span data-ttu-id="658ec-124">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="658ec-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="658ec-125">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="658ec-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="658ec-126">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="658ec-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="658ec-127">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="658ec-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="658ec-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="658ec-128">See also</span></span>

- <xref:System.Reflection.PortableExecutableKinds>
- [<span data-ttu-id="658ec-129">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="658ec-129">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="658ec-130">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="658ec-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
