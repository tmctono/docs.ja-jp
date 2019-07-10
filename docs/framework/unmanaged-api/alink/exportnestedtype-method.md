---
title: ExportNestedType メソッド
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedType
helpviewer_keywords:
- ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7dfaedad48291ac09f6959bc7b314ae0d9da76e5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742045"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="a8a93-102">ExportNestedType メソッド</span><span class="sxs-lookup"><span data-stu-id="a8a93-102">ExportNestedType Method</span></span>
<span data-ttu-id="a8a93-103">エクスポート可能として入れ子にされた型を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8a93-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="a8a93-104">[ExportType メソッド](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md)入れ子になったエクスポートの種類をこともできますが、このメソッドが高速です。</span><span class="sxs-lookup"><span data-stu-id="a8a93-104">The [ExportType Method](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8a93-105">構文</span><span class="sxs-lookup"><span data-stu-id="a8a93-105">Syntax</span></span>  
  
```cpp  
HRESULT ExportNestedType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="a8a93-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a8a93-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a8a93-107">エクスポートするアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="a8a93-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="a8a93-108">ファイルのトークンまたはエクスポート可能にする型を定義するファイルのアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="a8a93-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="a8a93-109">エクスポート可能にする型のトークンを入力します。</span><span class="sxs-lookup"><span data-stu-id="a8a93-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="a8a93-110">親の種類のトークンです。</span><span class="sxs-lookup"><span data-stu-id="a8a93-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="a8a93-111">エクスポートする完全修飾型名。</span><span class="sxs-lookup"><span data-stu-id="a8a93-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a8a93-112">`ComType` フラグなど`tdPublic`または`tdNested`します。</span><span class="sxs-lookup"><span data-stu-id="a8a93-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="a8a93-113">この値に渡される[DefineExportedType メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="a8a93-113">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="a8a93-114">エクスポートされた型のトークンを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a8a93-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8a93-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="a8a93-115">Return Value</span></span>  
 <span data-ttu-id="a8a93-116">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="a8a93-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8a93-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="a8a93-117">Requirements</span></span>  
 <span data-ttu-id="a8a93-118">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="a8a93-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8a93-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8a93-119">See also</span></span>

- [<span data-ttu-id="a8a93-120">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a8a93-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="a8a93-121">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a8a93-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="a8a93-122">ALink API</span><span class="sxs-lookup"><span data-stu-id="a8a93-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
