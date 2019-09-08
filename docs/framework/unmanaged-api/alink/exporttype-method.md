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
ms.openlocfilehash: 455f71c5b576d1b57db591dab2a3e59f8a5eed67
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777289"
---
# <a name="exporttype-method"></a><span data-ttu-id="3c2db-102">ExportType メソッド</span><span class="sxs-lookup"><span data-stu-id="3c2db-102">ExportType Method</span></span>
<span data-ttu-id="3c2db-103">型がエクスポート可能であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="3c2db-103">Specifies that a type is exportable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c2db-104">構文</span><span class="sxs-lookup"><span data-stu-id="3c2db-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c2db-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3c2db-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3c2db-106">エクスポート元のアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="3c2db-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="3c2db-107">エクスポート可能な型を定義するファイルのファイルトークンまたはアセンブリ ID。</span><span class="sxs-lookup"><span data-stu-id="3c2db-107">File token or assembly ID of file that defines the exportable type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="3c2db-108">エクスポート可能にする型のトークン。</span><span class="sxs-lookup"><span data-stu-id="3c2db-108">Token of type to be made exportable.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="3c2db-109">エクスポート可能にする完全修飾型名。</span><span class="sxs-lookup"><span data-stu-id="3c2db-109">Fully qualified type name to be made exportable.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3c2db-110">`ComType``tdPublic` や`tdNested`などのフラグ。</span><span class="sxs-lookup"><span data-stu-id="3c2db-110">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="3c2db-111">このパラメーターは、この[メソッド](../metadata/imetadataassemblyemit-defineexportedtype-method.md)に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="3c2db-111">This parameter may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="3c2db-112">エクスポートされた型のトークンを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3c2db-112">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c2db-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="3c2db-113">Return Value</span></span>  
 <span data-ttu-id="3c2db-114">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="3c2db-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c2db-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="3c2db-115">Requirements</span></span>  
 <span data-ttu-id="3c2db-116">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="3c2db-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c2db-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c2db-117">See also</span></span>

- [<span data-ttu-id="3c2db-118">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3c2db-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="3c2db-119">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3c2db-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="3c2db-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="3c2db-120">ALink API</span></span>](index.md)
