---
title: ExportType メソッド
ms.date: 03/30/2017
api_name:
- IALink.ExportType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportType
helpviewer_keywords:
- ExportType method
ms.assetid: 91a7ce63-f5b8-4f16-b2c4-e1d0baa88944
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 95ff27143453e7772b4a463fa66ca039bbb715fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59226918"
---
# <a name="exporttype-method"></a><span data-ttu-id="022a9-102">ExportType メソッド</span><span class="sxs-lookup"><span data-stu-id="022a9-102">ExportType Method</span></span>
<span data-ttu-id="022a9-103">型がエクスポート可能であるを指定します。</span><span class="sxs-lookup"><span data-stu-id="022a9-103">Specifies that a type is exportable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="022a9-104">構文</span><span class="sxs-lookup"><span data-stu-id="022a9-104">Syntax</span></span>  
  
```  
HRESULT ExportType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="022a9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="022a9-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="022a9-106">エクスポートするアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="022a9-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="022a9-107">ファイルのエクスポート可能な型を定義するファイルのトークンまたはアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="022a9-107">File token or assembly ID of file that defines the exportable type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="022a9-108">エクスポート可能にする型のトークンです。</span><span class="sxs-lookup"><span data-stu-id="022a9-108">Token of type to be made exportable.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="022a9-109">エクスポート可能にする完全修飾型名。</span><span class="sxs-lookup"><span data-stu-id="022a9-109">Fully qualified type name to be made exportable.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="022a9-110">`ComType` フラグなど`tdPublic`または`tdNested`します。</span><span class="sxs-lookup"><span data-stu-id="022a9-110">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="022a9-111">このパラメーターに渡される[DefineExportedType メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="022a9-111">This parameter may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="022a9-112">エクスポートされた型のトークンを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="022a9-112">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="022a9-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="022a9-113">Return Value</span></span>  
 <span data-ttu-id="022a9-114">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="022a9-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="022a9-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="022a9-115">Requirements</span></span>  
 <span data-ttu-id="022a9-116">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="022a9-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="022a9-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="022a9-117">See also</span></span>

- [<span data-ttu-id="022a9-118">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="022a9-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="022a9-119">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="022a9-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="022a9-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="022a9-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
