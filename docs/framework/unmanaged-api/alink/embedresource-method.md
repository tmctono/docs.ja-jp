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
ms.openlocfilehash: 24279870e7406de649df56e8aad31252513e95c7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446537"
---
# <a name="embedresource-method"></a><span data-ttu-id="96572-102">EmbedResource メソッド</span><span class="sxs-lookup"><span data-stu-id="96572-102">EmbedResource Method</span></span>
<span data-ttu-id="96572-103">埋め込みリソースを宣言します。</span><span class="sxs-lookup"><span data-stu-id="96572-103">Declares an embedded resource.</span></span> <span data-ttu-id="96572-104">このメソッドは、実際にはリソースを埋め込みません。</span><span class="sxs-lookup"><span data-stu-id="96572-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96572-105">構文</span><span class="sxs-lookup"><span data-stu-id="96572-105">Syntax</span></span>  
  
```cpp  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="96572-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="96572-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="96572-107">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="96572-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="96572-108">リソースが含まれているファイルのファイルトークンまたはアセンブリ ID。</span><span class="sxs-lookup"><span data-stu-id="96572-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="96572-109">リソースの名前。</span><span class="sxs-lookup"><span data-stu-id="96572-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="96572-110">RVA からのリソースのオフセット。</span><span class="sxs-lookup"><span data-stu-id="96572-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="96572-111">`mrPublic` や `mrPrivate`などのアクセシビリティフラグ。</span><span class="sxs-lookup"><span data-stu-id="96572-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="96572-112">これらのフラグは、を使用して、この[メソッド](../metadata/imetadataassemblyemit-defineexportedtype-method.md)に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="96572-112">These flags may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96572-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="96572-113">Return Value</span></span>  
 <span data-ttu-id="96572-114">メソッドが成功した場合は S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="96572-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96572-115">要件</span><span class="sxs-lookup"><span data-stu-id="96572-115">Requirements</span></span>  
 <span data-ttu-id="96572-116">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="96572-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96572-117">参照</span><span class="sxs-lookup"><span data-stu-id="96572-117">See also</span></span>

- [<span data-ttu-id="96572-118">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96572-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="96572-119">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96572-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="96572-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="96572-120">ALink API</span></span>](index.md)
