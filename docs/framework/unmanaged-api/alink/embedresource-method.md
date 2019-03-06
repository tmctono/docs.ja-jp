---
title: EmbedResource メソッド
ms.date: 03/30/2017
api_name:
- IALink.EmbedResource
- EmbedResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmbedResource
helpviewer_keywords:
- EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ffcd389f9b9e2e113fc45d2961a92790f4c57ae8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478051"
---
# <a name="embedresource-method"></a><span data-ttu-id="552b7-102">EmbedResource メソッド</span><span class="sxs-lookup"><span data-stu-id="552b7-102">EmbedResource Method</span></span>
<span data-ttu-id="552b7-103">埋め込みリソースを宣言します。</span><span class="sxs-lookup"><span data-stu-id="552b7-103">Declares an embedded resource.</span></span> <span data-ttu-id="552b7-104">このメソッドは、リソースを実際には埋め込まれません。</span><span class="sxs-lookup"><span data-stu-id="552b7-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="552b7-105">構文</span><span class="sxs-lookup"><span data-stu-id="552b7-105">Syntax</span></span>  
  
```  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="552b7-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="552b7-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="552b7-107">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="552b7-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="552b7-108">ファイル リソースを含むファイルのトークンまたはアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="552b7-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="552b7-109">リソースの名前。</span><span class="sxs-lookup"><span data-stu-id="552b7-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="552b7-110">リソースの RVA からのオフセット。</span><span class="sxs-lookup"><span data-stu-id="552b7-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="552b7-111">ユーザー補助フラグなど`mrPublic`と`mrPrivate`します。</span><span class="sxs-lookup"><span data-stu-id="552b7-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="552b7-112">これらのフラグに渡される[DefineExportedType メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="552b7-112">These flags may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="552b7-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="552b7-113">Return Value</span></span>  
 <span data-ttu-id="552b7-114">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="552b7-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="552b7-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="552b7-115">Requirements</span></span>  
 <span data-ttu-id="552b7-116">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="552b7-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="552b7-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="552b7-117">See also</span></span>
- [<span data-ttu-id="552b7-118">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="552b7-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="552b7-119">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="552b7-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="552b7-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="552b7-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
