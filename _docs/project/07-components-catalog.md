# 07-components-catalog.md

**Status**: Draft  
_Last Updated: 2025-01-16_

## 1. Purpose & Overview

This document serves as a centralized reference for all front-end components within our project, mirroring our planned `/components/` folder structure:

- **`/components/ui/`**: Houses **shadcn**-based UI components.  
- **`/components/global/`**: Holds global or “universal” components used across multiple pages/features (e.g., site headers, footers).  
- **`/components/blocks/`**: Common UI “block” patterns built from smaller `/ui/` elements (e.g., composite card layouts, hero banners).  
- **`/components/feature/[featureName]/`**: Feature-specific components that don’t warrant global scope (e.g., a specialized search widget for a single feature).  
- **`/components/page/[pageName]/`**: Page-specific components or partials (e.g., `UserProfileForm` for `page/user-profile`).

Our goals:  
1. Provide any developer or AI enough detail to use or replicate these components without needing the entire codebase in context.  
2. Keep each category well-documented to facilitate discovery and consistent usage.  
3. Indicate which components are planned, which are built, and how to use them.

See the **shorter** version at **`07.01-appr-components-catalog.md`** if you need a leaner, high-level reference.  
Remember to follow **`.cursorrules`** for naming, structure, and usage guidelines.  

---

## 2. `/components/ui/` (Shadcn-Based Components)

Below is a fleshed-out catalog of our **shadcn** UI components, with details on exports, properties, usage examples, and any relevant notes or dependencies. Each file is typically located in `/components/ui/[component-name].tsx`.

---

### 2.1 Accordion
- **Path**: `ui/accordion.tsx`  
- **Description**: Collapsible sections for showing/hiding content.  
- **Key Exports**: `Accordion`, `AccordionItem`, `AccordionTrigger`, `AccordionContent`  
- **Props**  
  - `Accordion` extends `@radix-ui/react-accordion` Root; typical props include `type`, `collapsible`, `defaultValue`.  
  - `AccordionItem` is each section container (`value` identifies the section).  
  - `AccordionTrigger` is the clickable trigger.  
  - `AccordionContent` is the collapsible panel content.  
- **Usage** example (no triple backticks):

import { Accordion, AccordionItem, AccordionTrigger, AccordionContent } from "@/components/ui/accordion";

export function ExampleAccordion() {
  return (
    <Accordion type="single" defaultValue="item-1" collapsible>
      <AccordionItem value="item-1">
        <AccordionTrigger>Section 1</AccordionTrigger>
        <AccordionContent>Content for section 1</AccordionContent>
      </AccordionItem>
      <AccordionItem value="item-2">
        <AccordionTrigger>Section 2</AccordionTrigger>
        <AccordionContent>Content for section 2</AccordionContent>
      </AccordionItem>
    </Accordion>
  );
}

- **Dependencies**: `@radix-ui/react-accordion`, `lucide-react` (icon)

---

### 2.2 AlertDialog
- **Path**: `ui/alert-dialog.tsx`  
- **Description**: A modal dialog for critical user confirmations.  
- **Key Exports**: `AlertDialog`, `AlertDialogTrigger`, `AlertDialogContent`, `AlertDialogHeader`, `AlertDialogFooter`, `AlertDialogTitle`, `AlertDialogDescription`, `AlertDialogAction`, `AlertDialogCancel`  
- **Usage**:

import {
  AlertDialog,
  AlertDialogTrigger,
  AlertDialogContent,
  AlertDialogHeader,
  AlertDialogFooter,
  AlertDialogTitle,
  AlertDialogDescription,
  AlertDialogAction,
  AlertDialogCancel
} from "@/components/ui/alert-dialog";

export function DeleteButton() {
  return (
    <AlertDialog>
      <AlertDialogTrigger>Delete Item</AlertDialogTrigger>
      <AlertDialogContent>
        <AlertDialogHeader>
          <AlertDialogTitle>Are you absolutely sure?</AlertDialogTitle>
          <AlertDialogDescription>
            This action cannot be undone.
          </AlertDialogDescription>
        </AlertDialogHeader>
        <AlertDialogFooter>
          <AlertDialogCancel>Cancel</AlertDialogCancel>
          <AlertDialogAction>Delete</AlertDialogAction>
        </AlertDialogFooter>
      </AlertDialogContent>
    </AlertDialog>
  );
}

- **Dependencies**: `@radix-ui/react-alert-dialog`, `lucide-react` (icon), `button.tsx`

---

### 2.3 Alert
- **Path**: `ui/alert.tsx`  
- **Description**: Displays an important, succinct message; supports variants like `default` or `destructive`.  
- **Key Exports**: `Alert`, `AlertTitle`, `AlertDescription`  
- **Usage**:

import { Alert, AlertTitle, AlertDescription } from "@/components/ui/alert";

export function ExampleAlert() {
  return (
    <Alert variant="destructive">
      <AlertTitle>Error</AlertTitle>
      <AlertDescription>Something went wrong!</AlertDescription>
    </Alert>
  );
}

- **Dependencies**: `class-variance-authority`, `lucide-react` (optional for icons)

---

### 2.4 AspectRatio
- **Path**: `ui/aspect-ratio.tsx`  
- **Description**: Enforces a consistent aspect ratio for child elements.  
- **Key Exports**: `AspectRatio`  
- **Usage**:

import { AspectRatio } from "@/components/ui/aspect-ratio";

export function Example() {
  return (
    <AspectRatio ratio={16 / 9}>
      <img src="some-image.jpg" alt="..." />
    </AspectRatio>
  );
}

- **Dependencies**: `@radix-ui/react-aspect-ratio`

---

### 2.5 Avatar
- **Path**: `ui/avatar.tsx`  
- **Description**: Circular user avatar with optional image or fallback text.  
- **Key Exports**: `Avatar`, `AvatarImage`, `AvatarFallback`  
- **Usage**:

import { Avatar, AvatarImage, AvatarFallback } from "@/components/ui/avatar";

export function ProfileAvatar() {
  return (
    <Avatar>
      <AvatarImage src="/user.png" alt="User" />
      <AvatarFallback>AB</AvatarFallback>
    </Avatar>
  );
}

- **Dependencies**: `@radix-ui/react-avatar`

---

### 2.6 Badge
- **Path**: `ui/badge.tsx`  
- **Description**: A small label for quick status/metadata. Variants: `default`, `secondary`, etc.  
- **Key Exports**: `Badge`  
- **Usage**:

import { Badge } from "@/components/ui/badge";

export function Status() {
  return <Badge variant="secondary">In Progress</Badge>;
}

- **Dependencies**: `class-variance-authority`

---

### 2.7 Breadcrumb
- **Path**: `ui/breadcrumb.tsx`  
- **Description**: Provides a breadcrumb navigation trail.  
- **Key Exports**: `Breadcrumb`, `BreadcrumbList`, `BreadcrumbItem`, `BreadcrumbLink`, `BreadcrumbSeparator`  
- **Usage**:

import {
  Breadcrumb,
  BreadcrumbList,
  BreadcrumbItem,
  BreadcrumbLink,
  BreadcrumbSeparator
} from "@/components/ui/breadcrumb";

export function ExampleBreadcrumbs() {
  return (
    <Breadcrumb>
      <BreadcrumbList>
        <BreadcrumbItem>
          <BreadcrumbLink href="/">Home</BreadcrumbLink>
        </BreadcrumbItem>
        <BreadcrumbSeparator />
        <BreadcrumbItem>
          <BreadcrumbLink href="/products">Products</BreadcrumbLink>
        </BreadcrumbItem>
        <BreadcrumbSeparator />
        <BreadcrumbItem>
          <BreadcrumbLink href="/products/123">Product 123</BreadcrumbLink>
        </BreadcrumbItem>
      </BreadcrumbList>
    </Breadcrumb>
  );
}

- **Dependencies**: `lucide-react` (icons)

---

### 2.8 Button
- **Path**: `ui/button.tsx`  
- **Description**: Reusable button with multiple variants and sizes.  
- **Key Exports**: `Button`  
- **Usage**:

import { Button } from "@/components/ui/button";

export function ExampleButton() {
  return (
    <Button variant="outline" size="sm">
      Click me
    </Button>
  );
}

- **Dependencies**: `class-variance-authority`, `@radix-ui/react-slot` (for `asChild`)

---

### 2.9 Calendar
- **Path**: `ui/calendar.tsx`  
- **Description**: A calendar/date-picker using `react-day-picker`.  
- **Key Exports**: `Calendar`  
- **Usage**:

import { Calendar } from "@/components/ui/calendar";

export function ExampleCalendar() {
  return <Calendar mode="single" selected={new Date()} onSelect={() => {}} />;
}

- **Dependencies**: `react-day-picker`, `lucide-react`, `button.tsx`

---

### 2.10 Card
- **Path**: `ui/card.tsx`  
- **Description**: A container for grouped info, with header/footer, etc.  
- **Key Exports**: `Card`, `CardHeader`, `CardTitle`, `CardDescription`, `CardContent`, `CardFooter`  
- **Usage**:

import {
  Card,
  CardHeader,
  CardTitle,
  CardDescription,
  CardContent,
  CardFooter
} from "@/components/ui/card";

export function ExampleCard() {
  return (
    <Card>
      <CardHeader>
        <CardTitle>Card Title</CardTitle>
        <CardDescription>A short summary or subheading</CardDescription>
      </CardHeader>
      <CardContent>Some content here.</CardContent>
      <CardFooter>Footer actions or info</CardFooter>
    </Card>
  );
}

- **Dependencies**: None aside from internal utility

---

### 2.11 Carousel
- **Path**: `ui/carousel.tsx`  
- **Description**: Embla-based carousel slider with next/prev controls.  
- **Key Exports**: `Carousel`, `CarouselContent`, `CarouselItem`, `CarouselPrevious`, `CarouselNext`  
- **Usage**:

import {
  Carousel,
  CarouselContent,
  CarouselItem,
  CarouselPrevious,
  CarouselNext
} from "@/components/ui/carousel";

export function ExampleCarousel() {
  return (
    <Carousel>
      <CarouselContent>
        <CarouselItem>Slide 1</CarouselItem>
        <CarouselItem>Slide 2</CarouselItem>
      </CarouselContent>
      <CarouselPrevious />
      <CarouselNext />
    </Carousel>
  );
}

- **Dependencies**: `embla-carousel-react`, `lucide-react`, `button.tsx`

---

### 2.12 Chart
- **Path**: `ui/chart.tsx`  
- **Description**: Recharts-based chart container, tooltip, and legend management.  
- **Key Exports**: `ChartContainer`, `ChartTooltip`, `ChartTooltipContent`, `ChartLegend`, `ChartLegendContent`  
- **Usage**:

import {
  ChartContainer,
  ChartTooltip,
  ChartTooltipContent,
  ChartLegend,
  ChartLegendContent
} from "@/components/ui/chart";
import { LineChart, Line } from "recharts";

export function ExampleChart() {
  return (
    <ChartContainer config={{ dataKey: { label: "Data" } }}>
      <LineChart data={[{ name: "A", value: 10 }, { name: "B", value: 20 }]}>
        <Line dataKey="value" />
        <ChartTooltip content={<ChartTooltipContent />} />
        <ChartLegend content={<ChartLegendContent />} />
      </LineChart>
    </ChartContainer>
  );
}

- **Dependencies**: `recharts`, optional theming, optional icon usage

---

### 2.13 Checkbox
- **Path**: `ui/checkbox.tsx`  
- **Description**: A basic checkbox for forms, extends Radix Checkbox.  
- **Key Exports**: `Checkbox`  
- **Usage**:

import { Checkbox } from "@/components/ui/checkbox";
import { useState } from "react";

export function ExampleCheckbox() {
  const [checked, setChecked] = useState(false);
  return <Checkbox checked={checked} onCheckedChange={setChecked} />;
}

- **Dependencies**: `@radix-ui/react-checkbox`, `lucide-react`

---

### 2.14 Collapsible
- **Path**: `ui/collapsible.tsx`  
- **Description**: A toggleable panel (simpler than Accordion).  
- **Key Exports**: `Collapsible`, `CollapsibleTrigger`, `CollapsibleContent`  
- **Usage**:

import {
  Collapsible,
  CollapsibleTrigger,
  CollapsibleContent
} from "@/components/ui/collapsible";

export function ExampleCollapsible() {
  return (
    <Collapsible>
      <CollapsibleTrigger>Toggle</CollapsibleTrigger>
      <CollapsibleContent>Hidden content</CollapsibleContent>
    </Collapsible>
  );
}

- **Dependencies**: `@radix-ui/react-collapsible`

---

### 2.15 Command
- **Path**: `ui/command.tsx`  
- **Description**: A Command palette (Cmd+K style) using `cmdk` plus a Dialog wrapper.  
- **Key Exports**: `Command`, `CommandDialog`, `CommandInput`, `CommandList`, `CommandItem`, `CommandGroup`, etc.  
- **Usage**:

import {
  CommandDialog,
  CommandInput,
  CommandList,
  CommandItem
} from "@/components/ui/command";

export function ExampleCommand() {
  return (
    <CommandDialog open={true}>
      <CommandInput placeholder="Type a command" />
      <CommandList>
        <CommandItem>First Command</CommandItem>
      </CommandList>
    </CommandDialog>
  );
}

- **Dependencies**: `cmdk`, `@radix-ui/react-dialog`, `lucide-react`

---

### 2.16 ContextMenu
- **Path**: `ui/context-menu.tsx`  
- **Description**: Right-click or long-press menu using Radix.  
- **Key Exports**: `ContextMenu`, `ContextMenuTrigger`, `ContextMenuContent`, `ContextMenuItem`, etc.  
- **Usage**:

import {
  ContextMenu,
  ContextMenuTrigger,
  ContextMenuContent,
  ContextMenuItem
} from "@/components/ui/context-menu";

export function ExampleContextMenu() {
  return (
    <ContextMenu>
      <ContextMenuTrigger>Right-click me</ContextMenuTrigger>
      <ContextMenuContent>
        <ContextMenuItem>Option 1</ContextMenuItem>
      </ContextMenuContent>
    </ContextMenu>
  );
}

- **Dependencies**: `@radix-ui/react-context-menu`, `lucide-react`

---

### 2.17 Dialog
- **Path**: `ui/dialog.tsx`  
- **Description**: A basic modal dialog, similar to AlertDialog but less strict.  
- **Key Exports**: `Dialog`, `DialogTrigger`, `DialogContent`, `DialogHeader`, `DialogFooter`, `DialogTitle`, `DialogDescription`, `DialogClose`  
- **Usage**:

import {
  Dialog,
  DialogTrigger,
  DialogContent,
  DialogHeader,
  DialogTitle,
  DialogDescription,
  DialogFooter
} from "@/components/ui/dialog";

export function ExampleDialog() {
  return (
    <Dialog>
      <DialogTrigger>Open</DialogTrigger>
      <DialogContent>
        <DialogHeader>
          <DialogTitle>Dialog Title</DialogTitle>
          <DialogDescription>Dialog description here</DialogDescription>
        </DialogHeader>
        <DialogFooter>Footer content</DialogFooter>
      </DialogContent>
    </Dialog>
  );
}

- **Dependencies**: `@radix-ui/react-dialog`, `lucide-react`

---

### 2.18 Drawer
- **Path**: `ui/drawer.tsx`  
- **Description**: Slide-in panel from bottom (mobile-friendly) powered by `vaul`.  
- **Key Exports**: `Drawer`, `DrawerTrigger`, `DrawerContent`, `DrawerHeader`, `DrawerFooter`, `DrawerTitle`, `DrawerDescription`, `DrawerClose`  
- **Usage**:

import {
  Drawer,
  DrawerTrigger,
  DrawerContent,
  DrawerHeader,
  DrawerTitle,
  DrawerFooter
} from "@/components/ui/drawer";

export function ExampleDrawer() {
  return (
    <Drawer>
      <DrawerTrigger>Open Drawer</DrawerTrigger>
      <DrawerContent>
        <DrawerHeader>
          <DrawerTitle>Drawer Title</DrawerTitle>
        </DrawerHeader>
        <div>Drawer body content</div>
        <DrawerFooter>Footer content</DrawerFooter>
      </DrawerContent>
    </Drawer>
  );
}

- **Dependencies**: `vaul`

---

### 2.19 DropdownMenu
- **Path**: `ui/dropdown-menu.tsx`  
- **Description**: A dropdown for actions or selections (Radix-based).  
- **Key Exports**: `DropdownMenu`, `DropdownMenuTrigger`, `DropdownMenuContent`, `DropdownMenuItem`, `DropdownMenuCheckboxItem`, etc.  
- **Usage**:

import {
  DropdownMenu,
  DropdownMenuTrigger,
  DropdownMenuContent,
  DropdownMenuItem
} from "@/components/ui/dropdown-menu";

export function ExampleDropdown() {
  return (
    <DropdownMenu>
      <DropdownMenuTrigger>Open Menu</DropdownMenuTrigger>
      <DropdownMenuContent>
        <DropdownMenuItem>Action 1</DropdownMenuItem>
      </DropdownMenuContent>
    </DropdownMenu>
  );
}

- **Dependencies**: `@radix-ui/react-dropdown-menu`, `lucide-react`

---

### 2.20 Form
- **Path**: `ui/form.tsx`  
- **Description**: React Hook Form integration helpers (e.g. `FormField`, `FormItem`, `FormLabel`, `FormControl`, etc.).  
- **Key Exports**: `Form`, `FormField`, `FormItem`, `FormLabel`, `FormControl`, `FormDescription`, `FormMessage`, `useFormField`  
- **Usage**:

import { useForm } from "react-hook-form";
import {
  Form,
  FormField,
  FormItem,
  FormLabel,
  FormControl,
  FormMessage
} from "@/components/ui/form";
import { Input } from "@/components/ui/input";

export function ExampleForm() {
  const form = useForm({ defaultValues: { email: "" } });

  return (
    <Form {...form}>
      <form onSubmit={form.handleSubmit(console.log)}>
        <FormField
          name="email"
          render={({ field }) => (
            <FormItem>
              <FormLabel>Email</FormLabel>
              <FormControl>
                <Input {...field} type="email" />
              </FormControl>
              <FormMessage />
            </FormItem>
          )}
        />
        <button type="submit">Submit</button>
      </form>
    </Form>
  );
}

- **Dependencies**: `react-hook-form`, `@radix-ui/react-label`

---

### 2.21 HoverCard
- **Path**: `ui/hover-card.tsx`  
- **Description**: A card that appears on hover/focus.  
- **Key Exports**: `HoverCard`, `HoverCardTrigger`, `HoverCardContent`  
- **Usage**:

import {
  HoverCard,
  HoverCardTrigger,
  HoverCardContent
} from "@/components/ui/hover-card";

export function ExampleHoverCard() {
  return (
    <HoverCard>
      <HoverCardTrigger>Hover me</HoverCardTrigger>
      <HoverCardContent>Tooltip-like content</HoverCardContent>
    </HoverCard>
  );
}

- **Dependencies**: `@radix-ui/react-hover-card`

---

### 2.22 InputOTP
- **Path**: `ui/input-otp.tsx`  
- **Description**: OTP (One-time password) input fields using `input-otp`.  
- **Key Exports**: `InputOTP`, `InputOTPGroup`, `InputOTPSlot`, `InputOTPSeparator`  
- **Usage**:

import { InputOTP, InputOTPGroup, InputOTPSlot } from "@/components/ui/input-otp";

export function ExampleOTP() {
  return (
    <InputOTP length={6} autoFocus onComplete={(value) => console.log(value)}>
      <InputOTPGroup>
        {[...Array(6)].map((_, i) => (
          <InputOTPSlot key={i} index={i} />
        ))}
      </InputOTPGroup>
    </InputOTP>
  );
}

- **Dependencies**: `input-otp`, `lucide-react` (for fallback icons)

---

### 2.23 Input
- **Path**: `ui/input.tsx`  
- **Description**: Base text input with tailwind styling.  
- **Key Exports**: `Input`  
- **Usage**:

import { Input } from "@/components/ui/input";

export function ExampleInput() {
  return <Input placeholder="Type here..." />;
}

- **Dependencies**: None (beyond internal utility)

---

### 2.24 Label
- **Path**: `ui/label.tsx`  
- **Description**: Label for form controls.  
- **Key Exports**: `Label`  
- **Usage**:

import { Label } from "@/components/ui/label";
import { Input } from "@/components/ui/input";

export function LabeledInput() {
  return (
    <div>
      <Label htmlFor="email">Email</Label>
      <Input id="email" type="email" />
    </div>
  );
}

- **Dependencies**: `@radix-ui/react-label`, `class-variance-authority`

---

### 2.25 Menubar
- **Path**: `ui/menubar.tsx`  
- **Description**: Horizontal menu bar for grouped actions.  
- **Key Exports**: `Menubar`, `MenubarMenu`, `MenubarTrigger`, `MenubarContent`, `MenubarItem`, `MenubarCheckboxItem`, `MenubarRadioItem`, etc.  
- **Usage**:

import {
  Menubar,
  MenubarMenu,
  MenubarTrigger,
  MenubarContent,
  MenubarItem
} from "@/components/ui/menubar";

export function ExampleMenubar() {
  return (
    <Menubar>
      <MenubarMenu>
        <MenubarTrigger>File</MenubarTrigger>
        <MenubarContent>
          <MenubarItem>New</MenubarItem>
        </MenubarContent>
      </MenubarMenu>
    </Menubar>
  );
}

- **Dependencies**: `@radix-ui/react-menubar`, `lucide-react`

---

### 2.26 NavigationMenu
- **Path**: `ui/navigation-menu.tsx`  
- **Description**: Multi-level menu system, e.g. top nav with submenus, using Radix NavigationMenu.  
- **Key Exports**: `NavigationMenu`, `NavigationMenuList`, `NavigationMenuItem`, `NavigationMenuTrigger`, `NavigationMenuContent`, etc.  
- **Usage**:

import {
  NavigationMenu,
  NavigationMenuList,
  NavigationMenuItem,
  NavigationMenuTrigger,
  NavigationMenuContent
} from "@/components/ui/navigation-menu";

export function ExampleNavMenu() {
  return (
    <NavigationMenu>
      <NavigationMenuList>
        <NavigationMenuItem>
          <NavigationMenuTrigger>Menu 1</NavigationMenuTrigger>
          <NavigationMenuContent>Dropdown content</NavigationMenuContent>
        </NavigationMenuItem>
      </NavigationMenuList>
    </NavigationMenu>
  );
}

- **Dependencies**: `@radix-ui/react-navigation-menu`, `lucide-react`

---

### 2.27 Pagination
- **Path**: `ui/pagination.tsx`  
- **Description**: Basic pagination controls (Previous, Next, page links).  
- **Key Exports**: `Pagination`, `PaginationContent`, `PaginationItem`, `PaginationLink`, `PaginationPrevious`, `PaginationNext`, `PaginationEllipsis`  
- **Usage**:

import {
  Pagination,
  PaginationContent,
  PaginationItem,
  PaginationLink,
  PaginationPrevious,
  PaginationNext,
  PaginationEllipsis
} from "@/components/ui/pagination";

export function ExamplePagination() {
  return (
    <Pagination>
      <PaginationContent>
        <PaginationItem>
          <PaginationPrevious />
        </PaginationItem>
        <PaginationItem>
          <PaginationLink>1</PaginationLink>
        </PaginationItem>
        <PaginationItem>
          <PaginationEllipsis />
        </PaginationItem>
        <PaginationItem>
          <PaginationLink>10</PaginationLink>
        </PaginationItem>
        <PaginationItem>
          <PaginationNext />
        </PaginationItem>
      </PaginationContent>
    </Pagination>
  );
}

- **Dependencies**: `lucide-react`, `button.tsx`

---

### 2.28 Popover
- **Path**: `ui/popover.tsx`  
- **Description**: A toggleable popover panel using Radix.  
- **Key Exports**: `Popover`, `PopoverTrigger`, `PopoverContent`  
- **Usage**:

import { Popover, PopoverTrigger, PopoverContent } from "@/components/ui/popover";

export function ExamplePopover() {
  return (
    <Popover>
      <PopoverTrigger>Open Popover</PopoverTrigger>
      <PopoverContent>Some content here</PopoverContent>
    </Popover>
  );
}

- **Dependencies**: `@radix-ui/react-popover`

---

### 2.29 Progress
- **Path**: `ui/progress.tsx`  
- **Description**: A progress bar with an animated indicator.  
- **Key Exports**: `Progress`  
- **Usage**:

import { Progress } from "@/components/ui/progress";

export function ExampleProgress() {
  return <Progress value={50} />;
}

- **Dependencies**: `@radix-ui/react-progress`

---

### 2.30 RadioGroup
- **Path**: `ui/radio-group.tsx`  
- **Description**: A group of radio buttons (Radix-based).  
- **Key Exports**: `RadioGroup`, `RadioGroupItem`  
- **Usage**:

import { RadioGroup, RadioGroupItem } from "@/components/ui/radio-group";

export function ExampleRadioGroup() {
  return (
    <RadioGroup defaultValue="option1">
      <div>
        <RadioGroupItem value="option1" id="r1" />
        <label htmlFor="r1">Option 1</label>
      </div>
      <div>
        <RadioGroupItem value="option2" id="r2" />
        <label htmlFor="r2">Option 2</label>
      </div>
    </RadioGroup>
  );
}

- **Dependencies**: `@radix-ui/react-radio-group`, `lucide-react`

---

### 2.31 Resizable
- **Path**: `ui/resizable.tsx`  
- **Description**: Panels that can be resized, using `react-resizable-panels`.  
- **Key Exports**: `ResizablePanelGroup`, `ResizablePanel`, `ResizableHandle`  
- **Usage**:

import {
  ResizablePanelGroup,
  ResizablePanel,
  ResizableHandle
} from "@/components/ui/resizable";

export function ExampleResizable() {
  return (
    <ResizablePanelGroup direction="horizontal">
      <ResizablePanel defaultSize={50}>Left Panel</ResizablePanel>
      <ResizableHandle withHandle />
      <ResizablePanel defaultSize={50}>Right Panel</ResizablePanel>
    </ResizablePanelGroup>
  );
}

- **Dependencies**: `react-resizable-panels`, `lucide-react`

---

### 2.32 ScrollArea
- **Path**: `ui/scroll-area.tsx`  
- **Description**: Custom scroll area with styling (Radix ScrollArea).  
- **Key Exports**: `ScrollArea`, `ScrollBar`  
- **Usage**:

import { ScrollArea } from "@/components/ui/scroll-area";

export function ExampleScrollArea() {
  return (
    <ScrollArea style={{ height: 200 }}>
      <p>Long content here...</p>
    </ScrollArea>
  );
}

- **Dependencies**: `@radix-ui/react-scroll-area`

---

### 2.33 Select
- **Path**: `ui/select.tsx`  
- **Description**: Styled select dropdown (Radix-based).  
- **Key Exports**: `Select`, `SelectTrigger`, `SelectContent`, `SelectItem`, etc.  
- **Usage**:

import {
  Select,
  SelectTrigger,
  SelectContent,
  SelectItem
} from "@/components/ui/select";

export function ExampleSelect() {
  return (
    <Select defaultValue="option1">
      <SelectTrigger />
      <SelectContent>
        <SelectItem value="option1">Option 1</SelectItem>
      </SelectContent>
    </Select>
  );
}

- **Dependencies**: `@radix-ui/react-select`, `lucide-react`

---

### 2.34 Separator
- **Path**: `ui/separator.tsx`  
- **Description**: A horizontal or vertical separator line.  
- **Key Exports**: `Separator`  
- **Usage**:

import { Separator } from "@/components/ui/separator";

export function ExampleSeparator() {
  return (
    <div>
      <div>Item above</div>
      <Separator />
      <div>Item below</div>
    </div>
  );
}

- **Dependencies**: `@radix-ui/react-separator`

---

### 2.35 Sheet
- **Path**: `ui/sheet.tsx`  
- **Description**: A side panel or “drawer” with flexible positioning (Radix-based).  
- **Key Exports**: `Sheet`, `SheetTrigger`, `SheetContent`, `SheetHeader`, `SheetFooter`, `SheetTitle`, `SheetDescription`, `SheetClose`  
- **Usage**:

import {
  Sheet,
  SheetTrigger,
  SheetContent,
  SheetHeader,
  SheetTitle,
  SheetFooter
} from "@/components/ui/sheet";

export function ExampleSheet() {
  return (
    <Sheet>
      <SheetTrigger>Open Sheet</SheetTrigger>
      <SheetContent side="right">
        <SheetHeader>
          <SheetTitle>Sheet Title</SheetTitle>
        </SheetHeader>
        <div>Sheet body content</div>
        <SheetFooter>Footer actions</SheetFooter>
      </SheetContent>
    </Sheet>
  );
}

- **Dependencies**: `@radix-ui/react-dialog`, `class-variance-authority`, `lucide-react`

---

### 2.36 Sidebar
- **Path**: `ui/sidebar.tsx`  
- **Description**: A collapsible or off-canvas sidebar system.  
- **Key Exports**: `Sidebar`, `SidebarProvider`, `SidebarContent`, `SidebarTrigger`, `SidebarGroup`, `SidebarMenu`, `SidebarMenuItem`, etc.  
- **Usage**:

import {
  SidebarProvider,
  Sidebar,
  SidebarTrigger,
  SidebarContent
} from "@/components/ui/sidebar";

export function ExampleLayout() {
  return (
    <SidebarProvider>
      <Sidebar>
        <SidebarTrigger />
        <SidebarContent>
          {/* nav items */}
        </SidebarContent>
      </Sidebar>
      {/* Main content */}
    </SidebarProvider>
  );
}

- **Dependencies**: `@radix-ui/react-slot`, `vaul` (for mobile drawer fallback), `lucide-react`

---

### 2.37 Skeleton
- **Path**: `ui/skeleton.tsx`  
- **Description**: A placeholder skeleton loader element.  
- **Key Exports**: `Skeleton`  
- **Usage**:

import { Skeleton } from "@/components/ui/skeleton";

export function ExampleSkeleton() {
  return <Skeleton className="h-4 w-1/2" />;
}

- **Dependencies**: None

---

### 2.38 Slider
- **Path**: `ui/slider.tsx`  
- **Description**: A Radix slider for selecting numeric ranges.  
- **Key Exports**: `Slider`  
- **Usage**:

import { Slider } from "@/components/ui/slider";

export function ExampleSlider() {
  return <Slider defaultValue={[50]} max={100} step={1} />;
}

- **Dependencies**: `@radix-ui/react-slider`

---

### 2.39 Sonner
- **Path**: `ui/sonner.tsx`  
- **Description**: A wrapper for the Sonner toast library (for theming).  
- **Key Exports**: `Toaster` (configured for theme)  
- **Usage**:

import { Toaster } from "@/components/ui/sonner";
import { toast } from "sonner";

export function ExampleSonner() {
  return (
    <>
      <button onClick={() => toast("Hello!")}>Show Toast</button>
      <Toaster />
    </>
  );
}

- **Dependencies**: `sonner`, `next-themes`

---

### 2.40 Switch
- **Path**: `ui/switch.tsx`  
- **Description**: A toggle switch control (Radix-based).  
- **Key Exports**: `Switch`  
- **Usage**:

import { Switch } from "@/components/ui/switch";
import { useState } from "react";

export function ExampleSwitch() {
  const [checked, setChecked] = useState(false);
  return <Switch checked={checked} onCheckedChange={setChecked} />;
}

- **Dependencies**: `@radix-ui/react-switch`

---

### 2.41 Table
- **Path**: `ui/table.tsx`  
- **Description**: Table elements (`Table`, `TableHeader`, `TableRow`, etc.) with tailwind styling.  
- **Key Exports**: `Table`, `TableHeader`, `TableBody`, `TableFooter`, `TableRow`, `TableHead`, `TableCell`, `TableCaption`  
- **Usage**:

import {
  Table,
  TableHeader,
  TableBody,
  TableFooter,
  TableRow,
  TableHead,
  TableCell,
  TableCaption
} from "@/components/ui/table";

export function ExampleTable() {
  return (
    <Table>
      <TableHeader>
        <TableRow>
          <TableHead>Name</TableHead>
          <TableHead>Value</TableHead>
        </TableRow>
      </TableHeader>
      <TableBody>
        <TableRow>
          <TableCell>Item 1</TableCell>
          <TableCell>123</TableCell>
        </TableRow>
      </TableBody>
      <TableFooter>
        <TableRow>
          <TableCell>Footer Info</TableCell>
          <TableCell>Some Data</TableCell>
        </TableRow>
      </TableFooter>
      <TableCaption>Optional Caption</TableCaption>
    </Table>
  );
}

- **Dependencies**: None

---

### 2.42 Tabs
- **Path**: `ui/tabs.tsx`  
- **Description**: A tabbed interface using Radix.  
- **Key Exports**: `Tabs`, `TabsList`, `TabsTrigger`, `TabsContent`  
- **Usage**:

import { Tabs, TabsList, TabsTrigger, TabsContent } from "@/components/ui/tabs";

export function ExampleTabs() {
  return (
    <Tabs defaultValue="tab1">
      <TabsList>
        <TabsTrigger value="tab1">Tab One</TabsTrigger>
        <TabsTrigger value="tab2">Tab Two</TabsTrigger>
      </TabsList>
      <TabsContent value="tab1">Content for Tab 1</TabsContent>
      <TabsContent value="tab2">Content for Tab 2</TabsContent>
    </Tabs>
  );
}

- **Dependencies**: `@radix-ui/react-tabs`

---

### 2.43 Textarea
- **Path**: `ui/textarea.tsx`  
- **Description**: A multiline text input.  
- **Key Exports**: `Textarea`  
- **Usage**:

import { Textarea } from "@/components/ui/textarea";

export function ExampleTextarea() {
  return <Textarea placeholder="Enter text here..." />;
}

- **Dependencies**: None

---

### 2.44 Toast / Toaster
- **Path**: `ui/toast.tsx`, `ui/toaster.tsx`  
- **Description**: Toast notifications. `Toast` components wrap Radix, while `Toaster` sets up the container.  
- **Key Exports**:  
  - From `toast.tsx`: `ToastProvider`, `ToastViewport`, `Toast`, `ToastTitle`, `ToastDescription`, `ToastAction`, `ToastClose`  
  - From `toaster.tsx`: `Toaster` (hook-based convenience for pushing toasts).  
- **Usage**:

import { Toaster } from "@/components/ui/toaster";
import { useToast } from "@/registry/default/hooks/use-toast";

export function ExampleToast() {
  const { toast } = useToast();

  return (
    <>
      <button onClick={() => toast({ title: "Hello", description: "World" })}>
        Show Toast
      </button>
      <Toaster />
    </>
  );
}

- **Dependencies**: `@radix-ui/react-toast`

---

### 2.45 Toggle & ToggleGroup
- **Path**: `ui/toggle.tsx`, `ui/toggle-group.tsx`  
- **Description**: A single toggle button or grouped toggles.  
- **Key Exports**: `Toggle`, `toggleVariants`, `ToggleGroup`, `ToggleGroupItem`  
- **Usage**:

import { Toggle } from "@/components/ui/toggle";
import { ToggleGroup, ToggleGroupItem } from "@/components/ui/toggle-group";

export function ExampleToggle() {
  return <Toggle>Click</Toggle>;
}

export function ExampleToggleGroup() {
  return (
    <ToggleGroup type="single" defaultValue="bold">
      <ToggleGroupItem value="bold">Bold</ToggleGroupItem>
      <ToggleGroupItem value="italic">Italic</ToggleGroupItem>
    </ToggleGroup>
  );
}

- **Dependencies**: `@radix-ui/react-toggle-group`, `class-variance-authority`

---

### 2.46 Tooltip
- **Path**: `ui/tooltip.tsx`  
- **Description**: Hover/click-based tooltips using Radix.  
- **Key Exports**: `Tooltip`, `TooltipTrigger`, `TooltipContent`, `TooltipProvider`  
- **Usage**:

import { Tooltip, TooltipTrigger, TooltipContent } from "@/components/ui/tooltip";

export function ExampleTooltip() {
  return (
    <Tooltip>
      <TooltipTrigger>Hover me</TooltipTrigger>
      <TooltipContent>Tooltip content</TooltipContent>
    </Tooltip>
  );
}

- **Dependencies**: `@radix-ui/react-tooltip`

---

## 3. `/components/global/`
Global or universal components used across multiple features or the entire site. Examples:

### SiteHeader
- **Path**: `global/site-header.tsx`  
- **Description**: Renders the primary site-wide header with nav links.  
- **Props / Variants**: `transparent`, `sticky`, etc.  
- **Usage**:
SiteHeader variant="sticky"  

- **Dependencies**: Possibly `Sidebar`, `Button`, etc.

*(We will add or expand entries here as we build them.)*

---

## 4. `/components/blocks/`
Common UI block patterns assembled from smaller `/ui/` elements. For example, a marketing “HeroBanner” that uses `Card`, `Button`, etc.

### HeroBanner
- **Path**: `blocks/hero-banner.tsx`  
- **Description**: A composite banner with a headline, subtext, and call-to-action button.  
- **Props**: { title, subtitle, ctaText, ctaHref }  
- **Usage**:
HeroBanner title="Welcome" subtitle="Check out our features" ctaText="Get Started" ctaHref="/signup"

- **Dependencies**: `Button`, `Card`, etc.

*(We will expand as we build more “block”-type components.)*

---

## 5. `/components/feature/[featureName]/`
Feature-specific components, relevant only within that domain. Example:

feature/auth/LoginForm.tsx
- **Description**: Renders the login form for authentication flow.
- **Usage**: <LoginForm onSuccess={...} />

*(As we build new features, we’ll add short documentation here.)*

---

## 6. `/components/page/[pageName]/`
Page-specific partials or smaller chunked components unique to a single page.

page/user-profile/UserDataCard.tsx
- **Description**: Shows user data in a card format for the user profile page.

*(These can also be documented in `[page-name].md` if more specialized detail is needed.)*

---

## 7. Adding or Defining a New Component

When creating **any** new component, follow these steps:

1. **Pick the Right Folder**  
   - `ui/` if it’s a universal, mostly style-based component (like a new button variant or form control).  
   - `global/` if used across the entire site.  
   - `blocks/` if it’s a higher-level composite block.  
   - `feature/[featureName]` for domain-specific components.  
   - `page/[pageName]` for page-specific partials.

2. **Create or Update an Entry Here**  
   - Provide the name, path, a brief description, key props/exports, usage snippet.

3. **Implement in Code**  
   - Follow **`.cursorrules`** for naming/structure. If any deviation is necessary, document it in your doc or a “v2” version.

4. **Reference in Page or Slice Docs**  
   - Whenever building or updating a page (`[page-name].md`), mention if you’re using or adding new components.

---
