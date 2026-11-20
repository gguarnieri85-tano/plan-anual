# Plan Anual

Calendario anual de trabajo, vacaciones y viajes.

## Supabase

Crea un proyecto en [supabase.com](https://supabase.com) y ejecuta en SQL Editor:

```sql
create table plan (
  id int primary key default 1,
  data jsonb,
  updated_at timestamptz default now()
);
alter table plan enable row level security;
create policy "anon full" on plan for all using (true) with check (true);
```

En la app (Opciones → Supabase) pega la URL del proyecto y la clave `anon`.

## GitHub Pages

Settings → Pages → Deploy from branch → `main` / root.
