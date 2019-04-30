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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6717c48fca14f2200f783a984594388ef3b29c15
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042472"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="1fc9c-102">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1fc9c-102">IMetaDataImport2 Interface</span></span>
<span data-ttu-id="1fc9c-103">拡張、 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)ジェネリック型の操作の機能を提供するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="1fc9c-103">Extends the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1fc9c-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="1fc9c-104">Methods</span></span>  
  
|<span data-ttu-id="1fc9c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1fc9c-105">Method</span></span>|<span data-ttu-id="1fc9c-106">説明</span><span class="sxs-lookup"><span data-stu-id="1fc9c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1fc9c-107">EnumGenericParamConstraints メソッド</span><span class="sxs-lookup"><span data-stu-id="1fc9c-107">EnumGenericParamConstraints Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="1fc9c-108">指定したトークンによって表されるジェネリック パラメーターに関連付けられているジェネリック パラメーターの制約の配列の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="1fc9c-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="1fc9c-109">EnumGenericParams メソッド</span><span class="sxs-lookup"><span data-stu-id="1fc9c-109">EnumGenericParams Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="1fc9c-110">トークンのジェネリック パラメーター トークンを指定した TypeDef または MethodDef に関連付けられた配列の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="1fc9c-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="1fc9c-111">EnumMethodSpecs メソッド</span><span class="sxs-lookup"><span data-stu-id="1fc9c-111">EnumMethodSpecs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="1fc9c-112">トークンに関連付けられた、指定した MethodDef または MemberRef MethodSpec トークンの配列の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="1fc9c-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="1fc9c-113">GetGenericParamConstraintProps メソッド</span><span class="sxs-lookup"><span data-stu-id="1fc9c-113">GetGenericParamConstraintProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="1fc9c-114">指定した制約トークンによって表されるジェネリック パラメーターの制約に関連付けられているメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="1fc9c-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="1fc9c-115">GetGenericParamProps メソッド</span><span class="sxs-lookup"><span data-stu-id="1fc9c-115">GetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="1fc9c-116">指定したトークンによって表されるジェネリック パラメーターに関連付けられているメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="1fc9c-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="1fc9c-117">GetMethodSpecProps メソッド</span><span class="sxs-lookup"><span data-stu-id="1fc9c-117">GetMethodSpecProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="1fc9c-118">指定した MethodSpec によって参照されるメソッドのメタデータ署名のトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="1fc9c-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="1fc9c-119">GetPEKind メソッド</span><span class="sxs-lookup"><span data-stu-id="1fc9c-119">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|<span data-ttu-id="1fc9c-120">ポータブル実行可能 (PE) でコードの性質を識別する値ファイルを取得、通常、DLL または EXE ファイルの現在のメタデータ スコープで定義されています。</span><span class="sxs-lookup"><span data-stu-id="1fc9c-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="1fc9c-121">GetVersionString メソッド</span><span class="sxs-lookup"><span data-stu-id="1fc9c-121">GetVersionString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|<span data-ttu-id="1fc9c-122">アセンブリのビルドに使用されたランタイムのバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="1fc9c-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1fc9c-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="1fc9c-123">Requirements</span></span>  
 <span data-ttu-id="1fc9c-124">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fc9c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fc9c-125">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1fc9c-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1fc9c-126">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="1fc9c-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1fc9c-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fc9c-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fc9c-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fc9c-128">See also</span></span>

- <xref:System.Reflection.PortableExecutableKinds>
- [<span data-ttu-id="1fc9c-129">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1fc9c-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="1fc9c-130">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1fc9c-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
