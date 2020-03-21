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
ms.openlocfilehash: 9ca2167e66ac3aa5bcc0e92ff357eed18d366c67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179415"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="ffbf9-102">ExportNestedType メソッド</span><span class="sxs-lookup"><span data-stu-id="ffbf9-102">ExportNestedType Method</span></span>
<span data-ttu-id="ffbf9-103">入れ子にされた型をエクスポート可能として指定します。</span><span class="sxs-lookup"><span data-stu-id="ffbf9-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="ffbf9-104">[エクスポートタイプ メソッド](exporttype-method.md)は、入れ子になった型をエクスポートすることもできますが、このメソッドの方が高速です。</span><span class="sxs-lookup"><span data-stu-id="ffbf9-104">The [ExportType Method](exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffbf9-105">構文</span><span class="sxs-lookup"><span data-stu-id="ffbf9-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ffbf9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ffbf9-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ffbf9-107">エクスポートするアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="ffbf9-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="ffbf9-108">エクスポート可能にする型を定義するファイル トークンまたはファイルのアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="ffbf9-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="ffbf9-109">エクスポート可能にする型のトークンを入力します。</span><span class="sxs-lookup"><span data-stu-id="ffbf9-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="ffbf9-110">親タイプのトークン。</span><span class="sxs-lookup"><span data-stu-id="ffbf9-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="ffbf9-111">エクスポートする完全修飾型名。</span><span class="sxs-lookup"><span data-stu-id="ffbf9-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ffbf9-112">`ComType`や`tdNested`などの`tdPublic`フラグ。</span><span class="sxs-lookup"><span data-stu-id="ffbf9-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="ffbf9-113">この値は、[エクスポートされた型のメソッド](../metadata/imetadataassemblyemit-defineexportedtype-method.md)に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="ffbf9-113">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="ffbf9-114">エクスポートされた型のトークンを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ffbf9-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ffbf9-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="ffbf9-115">Return Value</span></span>  
 <span data-ttu-id="ffbf9-116">メソッドが成功した場合は、S_OKを返します。</span><span class="sxs-lookup"><span data-stu-id="ffbf9-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffbf9-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="ffbf9-117">Requirements</span></span>  
 <span data-ttu-id="ffbf9-118">alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="ffbf9-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffbf9-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="ffbf9-119">See also</span></span>

- [<span data-ttu-id="ffbf9-120">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ffbf9-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="ffbf9-121">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ffbf9-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="ffbf9-122">ALink API</span><span class="sxs-lookup"><span data-stu-id="ffbf9-122">ALink API</span></span>](index.md)
