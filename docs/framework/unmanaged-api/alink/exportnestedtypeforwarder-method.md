---
title: ExportNestedTypeForwarder メソッド
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 050ed0bbd4da38bede5a56ff95d0243f5f3cf1da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789910"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="51e73-102">ExportNestedTypeForwarder メソッド</span><span class="sxs-lookup"><span data-stu-id="51e73-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="51e73-103">指定したアセンブリの型のテーブルを入れ子にされた型の型フォワーダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="51e73-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51e73-104">構文</span><span class="sxs-lookup"><span data-stu-id="51e73-104">Syntax</span></span>  
  
```  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="51e73-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="51e73-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="51e73-106">エクスポートするアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="51e73-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="51e73-107">ファイルの種類を定義するファイルのトークンまたはアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="51e73-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="51e73-108">型のトークンです。</span><span class="sxs-lookup"><span data-stu-id="51e73-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="51e73-109">親の種類のトークンです。</span><span class="sxs-lookup"><span data-stu-id="51e73-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="51e73-110">エクスポートする完全修飾型名。</span><span class="sxs-lookup"><span data-stu-id="51e73-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="51e73-111">`ComType` フラグなど`tdPublic`または`tdNested`します。</span><span class="sxs-lookup"><span data-stu-id="51e73-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="51e73-112">エクスポート型のトークンを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="51e73-112">Receives token of export type.</span></span> <span data-ttu-id="51e73-113">これは、入れ子にされた型の生成にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="51e73-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51e73-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="51e73-114">Return Value</span></span>  
 <span data-ttu-id="51e73-115">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="51e73-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51e73-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="51e73-116">Requirements</span></span>  
 <span data-ttu-id="51e73-117">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="51e73-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51e73-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="51e73-118">See also</span></span>

- [<span data-ttu-id="51e73-119">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="51e73-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="51e73-120">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="51e73-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="51e73-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="51e73-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
